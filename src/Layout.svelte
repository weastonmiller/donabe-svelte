<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  import { page } from '$app/stores';

  export const location = $page.url.pathname;

  const dispatch = createEventDispatcher();
  export let scroller = {
    scroll: 0,
    direction: true,
    delta: 0,
    initialScroll: 0,
  };
  const Scroll = (e: any) => {
    const scroll = e.target.scrollTop;

    scroller = {
      scroll,
      direction: scroll > scroller.scroll,
      delta: scroll - scroller.initialScroll,
      initialScroll:
        scroll > scroller.scroll != scroller.direction
          ? scroll
          : scroller.initialScroll,
    };

    dispatch('scroller', scroller);
  };
</script>

<main on:scroll={Scroll} style={`padding: ${location === '/' ? 0 : '1rem'}`}>
  <slot {scroller} />
</main>

<div class="header">
  <a href="/" class="title">Donabe</a>
  <div class="row"><a href="/browse">Browse</a><a href="/about">About</a></div>
</div>

<style>
  main {
    box-sizing: border-box;
    width: 100%;
    height: 100vh;
    overflow-y: auto;
    overflow-x: hidden;
    font-family: 'IBM Plex Mono';
    background-color: #fdf2e4;
  }

  .title {
    margin: 0;
    padding: 0;
    padding-left: 1rem;
    font-size: 22pt;
  }

  .header {
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 55px;
    transition: all 0.2s ease-in-out;
    background-color: #fdf2e4;
    color: #212529;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: 'IBM Plex Mono';
    font-weight: 600;
    box-shadow: 0 1px 10px 1px rgba(0, 0, 0, 0.12);
  }

  a {
    text-decoration: none;
    color: #212529;
    margin-left: 2rem;
    font-size: 16pt;
  }

  .row {
    padding-right: 2rem;
  }
</style>
