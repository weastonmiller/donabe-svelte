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
  <h6><slot /></h6>
{:else}
  {raw}
{/if}

<style>
  h1 {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
  }
  h2 {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
  }
  h3 {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
  }
  h4 {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
  }
  h5 {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
  }
  h6 {
    height: fit-content;
    font-style: italic;
    margin: 0;
    font-size: 12pt;
    font-weight: 200;
    align-self: center;
    margin-bottom: 1rem;
  }
</style>
