<script>
  import FadeIn from "$lib/components/FadeIn.svelte";
  import Hero from "./sections/Hero.svelte";
  import Features from "./sections/Features.svelte";
  import HowItWorks from "./sections/HowItWorks.svelte";
  import QA from "./sections/QA.svelte";
  import Reviews from "./sections/Reviews.svelte";
  import Journey from "./sections/Journey.svelte";
</script>

<main class="main">
  <FadeIn>
    <Hero></Hero>
  </FadeIn>
  <FadeIn>
    <Features></Features>
  </FadeIn>
  <FadeIn>
    <HowItWorks></HowItWorks>
  </FadeIn>
  <FadeIn>
    <QA></QA>
  </FadeIn>
  <FadeIn>
    <Reviews></Reviews>
  </FadeIn>
  <FadeIn>
    <Journey></Journey>
  </FadeIn>
</main>

<style>
  .main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
  }
</style>
