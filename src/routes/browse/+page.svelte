<script lang="ts">
  import Layout from '../../Layout.svelte';
  import { articles } from '../../articles';
</script>

<Layout>
  <div class="container">
    {#each articles as article}
      <a href={`/browse/${article.path}`}><h2>{article.title}</h2></a>
    {/each}
  </div></Layout
>

<style>
  .container {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    margin: 0;
    padding: 0;
    width: 100%;
    height: calc(100vh - 55px);
    background-color: #fdf2e4;
    margin-top: 55px;
    transition: 0.2s ease all;
  }

  a {
    background-color: #fdf2e4;
    color: #212529;
    text-decoration: none;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    opacity: 1;
    transition: 0.2s ease all;
  }

  a:hover {
    opacity: 0.7;
  }
</style>
