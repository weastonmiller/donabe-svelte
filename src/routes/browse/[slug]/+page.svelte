<script lang="ts">
  import Layout from '../../../Layout.svelte';
  import SvelteMarkdown from 'svelte-markdown';
  import MarkdownImage from '../../../components/MarkdownImage.svelte';

  let articlePromise = preload();

  export async function preload() {
    const path: any = window.location.pathname;
    const response = await fetch(
      `../../../../articles/${path.substring(8)}.md`
    );
    const article = await response.text();
    console.log(article);
    return article;
  }
</script>

<Layout>
  <div class="container">
    {#await articlePromise}
      <div />
    {:then article}
      <SvelteMarkdown source={article} renderers={{ image: MarkdownImage }} />
    {/await}
  </div></Layout
>

<style>
  .container {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    margin: 0;
    width: 100%;
    height: calc(100vh - 55px);
    background-color: #fdf2e4;
    margin-top: 55px;
    padding: 1rem;
  }

  .title {
    color: #212529;
    transition: 0.2s ease all;
    margin: 0;
  }
</style>
