<script lang="ts">
  import Layout from '../../Layout.svelte';
  import { articles } from '../../articles';

  import Masonry from 'svelte-bricks';

  let [minColWidth, maxColWidth, gap]: any = [300, 900, 20];
  let width: any, height: any;
</script>

<Layout>
  <div class="container">
    <Masonry
      items={articles}
      {minColWidth}
      {maxColWidth}
      {gap}
      idKey="_id"
      let:item
      bind:width
      bind:height
    >
      <a href={`/browse/${item.path}`}>
        <div>
          <img src={item.thumbnail} alt={item.title} />

          <p class="title">
            {item.title}
          </p>
          <p class="created">
            {item.created}
          </p>
        </div></a
      >
    </Masonry>
  </div></Layout
>

<style>
  .container {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    margin: 0;
    width: 100%;
    height: fit-content;
    margin-top: 55px;
    transition: 0.2s ease all;
  }

  a {
    font-size: 14pt;
    color: #212529;
    background: linear-gradient(to left, #fdf2e4 50%, #ffb86c 50%) right;
    background-size: 208% 100%;
    border-bottom: 2px solid #212529;
    border-left: none;
    border-right: none;
    border-top: none;
    transition: 0.2s ease all;
    font-family: 'IBM Plex Mono';
    font-weight: 400;
    cursor: pointer;
    display: flex;
    height: fit-content;
    padding: 0;
    text-decoration: none;
  }

  a:hover {
    background-position: left;
  }

  div {
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 100%;
    overflow: hidden;
  }

  img {
    object-fit: cover;
    width: 100%;
    height: auto;
  }

  .title {
    padding: 0 0.75rem;
    text-align: left;
    margin: 0.5rem 0;
  }

  .created {
    padding: 0 0.75rem;
    text-align: left;
    margin: 0;
    font-weight: 200;
    margin-bottom: 0.5rem;
  }
</style>
