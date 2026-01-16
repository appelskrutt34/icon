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

  let currentFeature = $state(0);
  let currentPhoneFeature = $state(0);

  function toggleFeature(index) {
    currentFeature = index;
  }

  function togglePhoneFeature(index) {
    if (currentPhoneFeature == index) {
      currentPhoneFeature = -1;
      return;
    }
    currentPhoneFeature = index;
  }
</script>

<section class="section base-container">
  <h1>Why People Choose ICON</h1>
  <p class="subtitle">
    Because success isn’t about working harder it’s about <br /> having the right
    coach by your side, 24/7.
  </p>

  <!-- Monitor -->
  <div class="section-content">
    <div class="features">
      {#each features as feature, i}
        <button class="feature" onclick={() => toggleFeature(i)}>
          <h2>{feature.title}</h2>
          <p>{feature.subtitle}</p>
        </button>
      {/each}
    </div>
    <img
      in:fade
      src={features[currentFeature].image}
      alt={features[currentFeature].altText}
      class="feature-image"
    />
  </div>

  <!-- Phone -->
  <div class="section-phone-content">
    {#each features as feature, i}
      <button
        class={currentPhoneFeature == i
          ? "feature-phone feature-phone-current"
          : "feature-phone"}
        onclick={() => togglePhoneFeature(i)}
      >
        <h2 class="feature-phone-title">
          {feature.title}
          {#if currentPhoneFeature == i}
            <ArrowUp color="fill: var(--red)"></ArrowUp>
          {:else}
            <ArrowDown></ArrowDown>
          {/if}
        </h2>
        <p>{feature.subtitle}</p>
        {#if currentPhoneFeature == i}
          <div in:slide out:slide>
            <img
              src={features[currentPhoneFeature].image}
              alt={features[currentPhoneFeature].altText}
              class="feature-phone-image"
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
    padding-top: 4em;
    padding-bottom: 4em;
    gap: 1em;
  }
  .section-content {
    width: 100%;
    display: flex;
    align-items: center;
    padding-top: 4em;
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
  .feature-image {
    width: 100%;
    max-height: 700px;
    object-fit: contain;
    flex: 1 1 0%;
  }
  .subtitle {
    color: var(--dark-white);
  }
  .feature {
    display: flex;
    flex-direction: column;
    gap: 1.2em;
    padding-bottom: 0.8em;
    border-bottom: var(--light-gray) solid 1px;
    transition: color 0.3s ease;
    text-align: left;
  }
  .feature:hover {
    cursor: pointer;
    color: var(--red) !important;
  }
  .section-phone-content {
    display: none;
  }

  /* When screen width is 768px or smaller */
  @media (max-width: 992px) {
    .section-content {
      display: none;
    }
    .section-phone-content {
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding-top: 1em;
      gap: 1em;
    }
    .feature-phone-image {
      width: 100%;
      object-fit: contain;
    }
    .feature-phone {
      display: flex;
      flex-direction: column;
      gap: 1.2em;
      padding-bottom: 0.8em;
      border-bottom: var(--light-gray) solid 1px;
      text-align: left;
      width: 100%;
    }
    .feature-phone-title {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .feature-phone-current {
      color: var(--red);
    }
  }
</style>
