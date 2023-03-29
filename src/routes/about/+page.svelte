<script>
  import Layout from '../../Layout.svelte';
</script>

<Layout let:scroller>
  <div class="container">
    <h1 class="title">Donabe</h1>
    <p>A bring your own ingredients markdown article viewer</p>
  </div></Layout
>

<style>
  .container {
    display: flex;
    flex-direction: column;
    margin: 0;
    padding: 0;
    height: 100%;
    width: 100%;
    align-items: center;
    justify-content: center;
    height: calc(100vh - 55px);
    background-color: #fdf2e4;
    margin-top: 55px;
  }

  .title {
    color: #212529;
    transition: 0.2s ease all;
    margin: 0;
  }
</style>
