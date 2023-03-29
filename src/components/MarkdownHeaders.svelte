<script lang="ts">
  export let depth: any;
  export let raw: any;
</script>

{#if depth === 1}
  <h1><slot /></h1>
{:else if depth === 2}
  <h2><slot /></h2>
{:else if depth === 3}
  <h3><slot /></h3>
{:else if depth === 4}
  <h4><slot /></h4>
{:else if depth === 5}
  <h5><slot /></h5>
{:else if depth === 6}
  <div>
    <p><slot /></p>
  </div>
{:else}
  {raw}
{/if}

<style>
  div {
    width: 100%;
    height: fit-content;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1rem;
  }
  p {
    height: fit-content;
    font-style: italic;
    margin: 0;
    font-weight: 200;
  }
</style>
