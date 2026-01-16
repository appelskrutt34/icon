<script>
  import ArrowDown from "$lib/components/icons/ArrowDown.svelte";
  import ArrowUp from "$lib/components/icons/ArrowUp.svelte";
  import { slide } from "svelte/transition";

  let qas = [
    {
      question: "What is ICON",
      answer:
        "ICON is your AI-powered personal fitness coach, built from the minds of real athletes and trainers. It learns about you your goals, habits, and preferences then creates a personalized plan that evolves daily.",
    },
    {
      question: "What makes ICON different from other fitness apps?",
      answer: "Answer",
    },
    {
      question: "How does ICON create my fitness plan",
      answer: "Answer",
    },
    {
      question: "Do I get a real coach or an AI coach?",
      answer: "Answer",
    },
    {
      question: "How much time do I need each day?",
      answer: "Answer",
    },
    {
      question: "Is ICON free?",
      answer: "Answer",
    },
    {
      question: "Can I connect my fitness devices or wearables?",
      answer: "Answer",
    },
    {
      question: "I’m a beginner, is ICON right for me?",
      answer: "Answer",
    },
    {
      question: "Is ICON available worldwide?",
      answer: "Answer",
    },
    {
      question: "What can I track inside ICON?",
      answer: "Answer",
    },
  ];
  let expandedQuestion = $state(0);

  function toggleQuestion(index) {
    expandedQuestion = expandedQuestion === index ? -1 : index;
  }
</script>

<section class="section l-container l-vertical-margin">
  <div class="section__heading__layout">
    <h1>Got Questions? We've <br /> got answers.</h1>
    <p class="section__subtitle">
      Learn how ICON helps you train smarter, stay consistent, and <br /> take full
      control of your fitness journey.
    </p>
  </div>
  <div class="qas">
    {#each qas as qa, i}
      <button
        class={expandedQuestion == i ? "qa active" : "qa"}
        onclick={() => toggleQuestion(i)}
      >
        <h2 class="qa__question">
          {qa.question}
          {#if expandedQuestion == i}
            <ArrowUp></ArrowUp>
          {:else}
            <ArrowDown></ArrowDown>
          {/if}
        </h2>
        {#if expandedQuestion == i}
          <p in:slide out:slide class="qa__answer">{qa.answer}</p>
        {/if}
      </button>
    {/each}
  </div>
</section>

<style>
  .section {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
  }
  .section__heading__layout {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin-bottom: 4em;
  }
  .section__subtitle {
    color: var(--dark-white);
  }
  .qa {
    text-align: left;
    padding-right: 1em;
    padding-left: 1em;
    padding-top: 1em;
    padding-bottom: 1em;
    border-radius: 16px;
    background-color: var(--light-gray);
  }
  .qas {
    display: flex;
    flex-direction: column;
    gap: 0.5em;
    width: 700px;
  }
  .qa__question {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .qa__answer {
    margin-top: 0.5em;
    margin-bottom: 0.5em;
    margin-right: 1em;
  }
  .qa:hover .qa__question {
    color: var(--red);
  }
  .qa:hover :global(svg) {
    fill: var(--red);
  }
  .qa.active .qa__question {
    color: var(--red);
  }
  .qa.active :global(svg) {
    fill: var(--red);
  }

  @media (max-width: 1400px) {
    .section {
      width: 100%;
    }

    .section__heading__layout {
      flex-direction: column;
      text-align: center;
      gap: 1em;
    }
  }

  @media (max-width: 992px) {
    .qas {
      width: 100%;
    }
  }
</style>
