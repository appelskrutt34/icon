<script>
  import { onMount } from "svelte";

  let visible = $state(false);
  let element;

  onMount(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        visible = entry.isIntersecting;
      },
      {
        threshold: 0.15,
      }
    );

    observer.observe(element);

    return () => observer.disconnect();
  });
</script>

<div bind:this={element} class="fade__section {visible ? 'visible' : ''}">
  <slot />
</div>

<style>
  .fade__section {
    width: 100%;
    display: flex;
    justify-content: center;
    opacity: 0;
    transform: translateY(24px);
    transition:
      opacity 0.6s ease,
      transform 0.6s ease;
    will-change: opacity, transform;
  }

  .fade__section.visible {
    opacity: 1;
    transform: translateY(0);
  }
</style>
