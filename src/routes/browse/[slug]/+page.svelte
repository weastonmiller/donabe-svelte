<script lang="ts">
  import Layout from '../../../Layout.svelte';
  import SvelteMarkdown from 'svelte-markdown';
  import MarkdownImage from '../../../components/MarkdownImage.svelte';
  import MarkdownHeaders from '../../../components/MarkdownHeaders.svelte';
  import MarkdownParagraph from '../../../components/MarkdownParagraph.svelte';
  import MarkdownHR from '../../../components/MarkdownHR.svelte';
  import MarkdownBlockquote from '../../../components/MarkdownBlockquote.svelte';

  let articlePromise = preload();

  export async function preload() {
    const path: any = window.location.pathname;
    const response = await fetch(
      `../../../../articles/${path.substring(8)}.md`
    );
    const article = await response.text();
    return article;
  }
</script>

<Layout>
  <div class="container">
    {#await articlePromise}
      <div />
    {:then article}
      <SvelteMarkdown
        source={article}
        renderers={{
          image: MarkdownImage,
          heading: MarkdownHeaders,
          paragraph: MarkdownParagraph,
          hr: MarkdownHR,
          blockquote: MarkdownBlockquote,
        }}
      />
    {/await}
  </div>
</Layout>

<style>
  .container {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    margin: 0;
    width: 100%;
    height: fit-content;
    background-color: #fdf2e4;
    margin-top: 55px;
    padding: 1rem;
  }
</style>
