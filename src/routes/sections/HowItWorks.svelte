<script>
  let steps = [
    {
      title: "Take the Fitness Quiz",
      description:
        "Complete the fitness quiz and receive a hyper personalised fitness report",
      image: "./step-1.png",
      imageAltText: "alt text",
    },
    {
      title: "Your Expert Coach, Always On",
      description:
        "Talk to your Icon 24/7/365 - A real-life, superpowered expert in your phone",
      image: "./step-2.png",
      imageAltText: "alt text",
    },
    {
      title: "Stay on Track, Every Single Day",
      description:
        "Customise and track the fitness metrics you care about - Your Icon will help you succeed every day, even when things don’t go to plan",
      image: "./step-3.png",
      imageAltText: "alt text",
    },
  ];
</script>

<section class="section l-vertical-margin">
  <h1>How It Works</h1>
  <p class="section__subtitle">
    Your journey to elite performance starts in <br /> three simple steps.
  </p>

  <div class="steps">
    {#each steps as step}
      <div class="step">
        <img src={step.image} alt={step.imageAltText} class="step__image" />
        <p class="step__title l-medium-font">{step.title}</p>
        <p class="step__description">{step.description}</p>
      </div>
    {/each}
  </div>
</section>

<style>
  .section {
    text-align: center;
    display: flex;
    align-items: center;
    flex-direction: column;
    margin-left: 0.8em;
    margin-right: 0.8em;
    max-width: var(--max-w);
  }

  .section__subtitle {
    margin-top: 1em;
    margin-bottom: 4em;
  }

  .steps {
    text-align: center;
    display: flex;
    justify-content: center;
    gap: 1.5em;
    width: 100%;
  }

  .step {
    padding-right: 1em;
    padding-left: 1em;
    padding-top: 1em;
    padding-bottom: 1em;
    border-radius: 16px;
    background-color: var(--gray);
    width: 100%;
    flex: 1 1 0%;
  }
  .step__image {
    max-width: 100%;
    width: 100%;
    object-fit: contain;
  }
  .step__title {
    margin-top: 1em;
    margin-bottom: 1em;
    font-weight: 600;
  }
  .section__subtitle,
  .step__description {
    color: var(--dark-white);
  }

  @media (max-width: 992px) {
    .section {
      max-width: 100vw;
      overflow-x: hidden;
      margin-left: 0;
      margin-right: 0;
    }
    .steps {
      display: flex;
      overflow-x: auto;
      scroll-snap-type: x mandatory;
      -webkit-overflow-scrolling: touch;
      justify-content: flex-start;
      gap: 1em;
      padding-left: 1em;
      padding-right: 1em;
      box-sizing: border-box;
    }

    .step {
      max-width: 300px;
      flex: 0 0 80%;
      scroll-snap-align: center;
    }
  }
</style>
