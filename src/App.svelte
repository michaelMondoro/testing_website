<script>
  import { onMount } from "svelte";
  import ApiPage from "./ip_api/ApiPage.svelte";
  import { fade } from "svelte/transition";
  import WelcomePage from "./WelcomePage.svelte";
  import BrainBrewPage from "./BrainBrewPage.svelte";
  import { currentPage } from "./store";

  let ready = false;
  onMount(() => { 
    ready = true;
    if (!$currentPage) currentPage.set("home")
  })
</script>
<main>
  {#if ready}
    <div class="header" in:fade={{ duration: 1000 }}>
      <span class="header-item name">
          <span class="">Michael Mondoro | <b>Software Engineer</b></span>
      </span>
      <div class="links header-item">
        <button on:click={() => currentPage.set("home")} class="{$currentPage=="home" ? 'selected':''}">portfolio</button>
        <button on:click={() => currentPage.set("ip api")} class="{$currentPage=="ip api" ? 'selected':''}">geo ip</button>
        <button on:click={() => currentPage.set("brainbrew")} class="{$currentPage=="brainbrew" ? 'selected':''}">BrainBrew</button>
      </div>
      <span class="header-item">
        <a class="hover" href="https://github.com/michaelMondoro" target="_blank"><i class="fa fa-github hover icon"></i></a>
        <a class="hover" href="https://www.linkedin.com/in/michael-mondoro-8b7423151/" target="_blank"><i class="fa fa-linkedin hover icon"></i></a>
    </span>
    </div>
  {/if}
  {#if $currentPage === "home"}
    <WelcomePage />
  {:else if $currentPage === "ip api"}
    <ApiPage />
  {:else if $currentPage == "brainbrew"}
    <BrainBrewPage />
  {/if}
  <br><br>
</main>

  
<style>
main {
  width: 100%;
  height: 100%;
}

a {
  color: var(--main-color);
}

button {
  all: unset;
  padding: .5em 1em;
  cursor: pointer;
  transition: all .1s;
}
button:hover {
  transform: scale(1.07);
}

.selected {
  border-bottom: solid var(--main-color) 1px;
}


@media only screen and (max-width: 700px) {
  .name {
    display: none;
  }
}
</style>
