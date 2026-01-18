<script>
  import ArrowDown from "$lib/components/icons/ArrowDown.svelte";
  import ArrowUp from "$lib/components/icons/ArrowUp.svelte";
  import { slide } from "svelte/transition";

  let qas = [
    {
      question: "What is ICON?",
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
        <p class="l-medium-font qa__question">
          {String(i + 1).padStart(2, "0")}
          {" "}
          {qa.question}
          {#if expandedQuestion == i}
            <ArrowUp></ArrowUp>
          {:else}
            <ArrowDown></ArrowDown>
          {/if}
        </p>
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
    margin-bottom: 4rem;
  }
  .section__subtitle {
    color: var(--light-gray);
  }
  .qas {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    width: 700px;
  }
  .qa {
    position: relative;
    padding: 1rem;
    overflow: hidden;
    transition: color 0.3s ease;
    text-align: left;
    padding-right: 1rem;
    padding-left: 1rem;
    padding-top: 1rem;
    padding-bottom: 1rem;
    border-radius: 16px;
    background-color: var(--gray);
  }
  .qa.active::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 2px;
    border-radius: 16px;
    background: linear-gradient(90deg, var(--blue), var(--red), var(--blue));
    background-size: 200% 200%;
    -webkit-mask:
      linear-gradient(#fff 0 0) content-box,
      linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    pointer-events: none;
    z-index: 0;
    transition: color 0.3s ease;
  }
  .qa__question {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-weight: 600;
    transition: color 0.3s ease;
  }
  .qa__answer {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
    margin-right: 1rem;
    color: var(--light-gray);
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
      gap: 1rem;
    }
  }

  @media (max-width: 992px) {
    .qas {
      width: 100%;
    }
  }
</style>
