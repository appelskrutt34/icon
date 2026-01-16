<script>
  import FadeIn from "$lib/components/FadeIn.svelte";
  import Hero from "./sections/Hero.svelte";
  import Features from "./sections/Features.svelte";
</script>

<main class="main">
  <FadeIn>
    <Hero></Hero>
  </FadeIn>
  <FadeIn>
    <Features></Features>
  </FadeIn>
</main>

<style>
  .main {
    display: flex;
    flex-direction: column;
    align-items: center;

    width: 100%;
  }
</style>
