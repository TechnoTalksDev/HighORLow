<script>
  import { onMount } from 'svelte';
  import svelteLogo from './assets/svelte.svg'
  import Counter from './lib/Counter.svelte'
  import Random from './lib/Random.svelte';
  import Update from './lib/Random.svelte';
</script>

<main>
  <h1><span class="hot">High</span> <span class="or">OR</span> <span class="cold">Low</span></h1>

  <p style="margin-bottom: 0px;"class="read-the-docs">A simple number guessing game! Guess a number between <strong>1 to 100</strong>. A hint will appear saying <strong>High OR Low</strong>. Enjoy this simple but addicting game!</p>

  <div class="card">
    <Random/>
  </div>
  
  <p>
    A simple high or low game!
  </p>

  <footer class="read-the-docs">
    <p>
      Built by <a href="https://www.technotalks.net" target="new">TechnoTalks</a> with ❤️<br/>
      Powered by Vite + Svelte
    </p>
      <!-- svelte-ignore security-anchor-rel-noreferrer -->
      <a href="https://vitejs.dev" target="_blank"> 
        <img src="/vite.svg" class="logo" alt="Vite Logo" />
      </a>
      <!-- svelte-ignore security-anchor-rel-noreferrer -->
      <a href="https://svelte.dev" target="_blank"> 
        <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
      </a>
  </footer>
</main>

<style>
  .logo {
    height: 10%;
    padding: .1em 0.5em 0.1em 0.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: rgba(255, 255, 255, 0.819);
    width: 400px;
    filter: drop-shadow(3em black);
  }
  .hot {
    color: red;
    filter: drop-shadow(0 0 2.5px red);
  }
  .hot:hover {
    filter: drop-shadow(0 0 5px red);
    transition: 0.5s;
  }
  .hot:not(:hover) {
    transition: 0.5s;
  }
  .cold {
    color: skyblue;
    filter: drop-shadow(0 0 2.5px skyblue);
  }
  .cold:hover {
    filter: drop-shadow(0 0 5px skyblue);
    transition: 0.5s;
  }
  .cold:not(:hover) {
    transition: 0.5s;
  }
  .or:hover {
    filter: drop-shadow(0 0 2.5px white);
    transition: 0.5s;
  }
  .or:not(:hover) {
    transition: 5s;
  }
</style>
