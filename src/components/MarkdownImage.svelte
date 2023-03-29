<script lang="ts">
  export let href: string = '';
  export let text: string = '';
</script>

<div class="container">
  <div class="wrapper">
    <img src={href} alt={text} class="custom-image" />
  </div>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    height: fit-content;
    width: 100%;
    overflow: hidden;
    align-items: center;
    justify-content: center;
  }
  .wrapper {
    display: flex;
    flex-direction: column;
    height: fit-content;
    width: fit-content;
    overflow: hidden;
  }
  .custom-image {
    width: 100%;
    height: auto;
    object-fit: cover;
  }
</style>
