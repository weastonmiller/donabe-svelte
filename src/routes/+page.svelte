<script>
  import Layout from '../Layout.svelte';
</script>

<Layout>
  <div class="container">
    <img
      src="https://assets.bonappetit.com/photos/57c59f63a184a3c9209db716/4:3/w_4911,h_3683,c_limit/hot-pot-donabe-chopsticks.jpg"
      alt=""
    />
    <div class="centered">
      <h1 class="title">Donabe</h1>
      <a href="/browse">Browse Articles 🠒</a>
    </div>
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
  }

  img {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }

  .centered {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: fit-content;
  }

  .title {
    color: #212529;
    background-color: #fdf2e4;
    padding: 0rem 0.5rem;
    font-size: 42pt;
    transition: 0.2s ease all;
  }

  a {
    font-size: 14pt;
    color: #212529;
    background-color: #fdf2e4;
    padding: 0 0.5rem;
    transition: 0.2s ease all;
    border: none;
    font-family: IBM Plex Mono;
    font-weight: 400;
    cursor: pointer;
    text-decoration: none;
  }
</style>
