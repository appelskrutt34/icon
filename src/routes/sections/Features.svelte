<script>
  import ArrowDown from "$lib/components/icons/ArrowDown.svelte";
  import ArrowUp from "$lib/components/icons/ArrowUp.svelte";
  import { fade, slide } from "svelte/transition";

  let features = [
    {
      title: "Personalised plans",
      subtitle:
        "Your goals, your schedule, your body fully customised by AI and athlete expertise",
      image: "./phone.png",
      altText: "image alt text",
    },
    {
      title: "Track everything",
      subtitle:
        "From workouts to recovery, nutrition to mood every metric that matters, all in one place.",
      image: "./phone.png",
      altText: "image alt text",
    },
    {
      title: "AI-powered chat",
      subtitle:
        "Talk to your Icon anytime, anywhere. Get instant feedback, guidance, and motivation 24/7.",
      image: "./phone.png",
      altText: "image alt text",
    },
    {
      title: "Expert-crafted Icons",
      subtitle:
        "Each Icon is built by real athletes and coaches bringing elite knowledge straight to your pocket.",
      image: "./phone.png",
      altText: "image alt text",
    },
  ];

  let activeFeature = $state(0);
  let expandedFeature = $state(0);

  function selectFeature(index) {
    activeFeature = index;
  }

  function toggleFeature(index) {
    expandedFeature = expandedFeature === index ? -1 : index;
  }
</script>

<section class="section l-container l-vertical-margin">
  <h1>Why People Choose ICON</h1>
  <p class="section__subtitle">
    Because success isn’t about working harder it’s about <br /> having the right
    coach by your side, 24/7.
  </p>

  <!-- Monitor -->
  <div class="section__layout">
    <div class="features">
      {#each features as feature, i}
        <button class="feature" onclick={() => selectFeature(i)}>
          <h2>{feature.title}</h2>
          <p class="feature__description">{feature.subtitle}</p>
        </button>
      {/each}
    </div>
    <img
      in:fade
      src={features[activeFeature].image}
      alt={features[activeFeature].altText}
      class="feature__image"
    />
  </div>

  <!-- Phone -->
  <div class="section__layout--phone">
    {#each features as feature, i}
      <button
        class={expandedFeature == i ? "feature feature--active" : "feature"}
        onclick={() => toggleFeature(i)}
      >
        <h2 class="feature__title--phone">
          {feature.title}
          {#if expandedFeature == i}
            <ArrowUp color="fill: var(--red)"></ArrowUp>
          {:else}
            <ArrowDown></ArrowDown>
          {/if}
        </h2>
        <p class="feature__description">{feature.subtitle}</p>
        {#if expandedFeature == i}
          <div in:slide out:slide>
            <img
              src={features[expandedFeature].image}
              alt={features[expandedFeature].altText}
              class="feature__image"
            />
          </div>
        {/if}
      </button>
    {/each}
  </div>
</section>

<style>
  .section {
    display: flex;
    justify-content: center;
    text-align: center;
    align-items: center;
    flex-direction: column;
  }
  .section__layout {
    width: 100%;
    display: flex;
    align-items: center;
    gap: 5em;
  }
  .features {
    width: 100%;
    flex: 1 1 0%;
    text-align: left;
    display: flex;
    gap: 1em;
    flex-direction: column;
  }
  .feature__image {
    width: 100%;
    max-height: 700px;
    object-fit: contain;
    flex: 1 1 0%;
  }

  .section__subtitle {
    color: var(--dark-white);
    margin-top: 1em;
    margin-bottom: 4em;
  }

  .feature {
    display: flex;
    flex-direction: column;
    border-bottom: var(--light-gray) solid 1px;
    transition: color 0.3s ease;
    text-align: left;
    width: 100%;
  }

  .feature__description {
    margin-top: 1em;
    margin-bottom: 1em;
  }

  .feature:hover {
    cursor: pointer;
    color: var(--red) !important;
  }
  .feature--active {
    color: var(--red);
  }
  .section__layout--phone {
    display: none;
  }

  @media (max-width: 992px) {
    .section__layout {
      display: none;
    }
    .section__layout--phone {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 1em;
    }
    .feature__image {
      width: 100%;
      max-height: 600px;
      object-fit: contain;
      margin-top: 1em;
      margin-bottom: 1em;
    }
    .feature__title--phone {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
  }
</style>
