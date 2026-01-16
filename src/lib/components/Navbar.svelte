<script>
  import { fade, scale, slide } from "svelte/transition";
  import Close from "./icons/Close.svelte";
  import Menu from "./icons/Menu.svelte";

  let openPhoneMenu = $state(false);
</script>

<div class="header">
  <!-- Monitor -->
  <nav class="nav base-container">
    <a href="/" class="link">Icon</a>
    <div class="nav-pages">
      <a href="/" class="link">Home</a>
      <a href="/" class="link">Trainers</a>
      <a href="/" class="link">Pricing</a>
      <a href="/" class="link">About Us</a>
      <a href="/" class="link">Contact Us</a>
    </div>
    <button class="link">Join Waitlist</button>
  </nav>

  <!-- Phone -->
  <nav class="nav-phone base-container">
    <div class="nav-phone-pages">
      <a href="/">Icon</a>
      {#if openPhoneMenu === true}
        <button in:scale onclick={() => (openPhoneMenu = false)}>
          <Close></Close>
        </button>
      {:else}
        <button in:scale onclick={() => (openPhoneMenu = true)}
          ><Menu></Menu></button
        >
      {/if}
    </div>
    {#if openPhoneMenu === true}
      <div in:slide out:slide class="phone-menu">
        <a href="/">Home</a>
        <a href="/">Trainers</a>
        <a href="/">Pricing</a>
        <a href="/">About Us</a>
        <a href="/">Contact Us</a>
      </div>
    {/if}
  </nav>
</div>

<style>
  .header {
    display: flex;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 50;
    color: var(--white);
    background-color: var(--background);
    border-bottom: 1px solid var(--light-gray);
  }

  .nav-pages {
    display: flex;
    justify-content: center;
    gap: 28px;
  }

  .link {
    transition: color 0.3s ease;
  }

  .link:hover {
    color: var(--red);
  }

  .nav {
    padding-top: 26px;
    padding-bottom: 26px;
    display: flex;
    justify-content: space-between;
  }

  .nav-phone {
    width: 100%;
    display: none;
    flex-direction: column;
    padding-top: 26px;
    padding-bottom: 26px;
  }

  .nav-phone-pages {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .phone-menu {
    background-color: var(--background);
    display: flex;
    flex-direction: column;
    gap: 18px;
    transition: all 0.3s ease;
    padding-top: 26px;
    padding-bottom: 26px;
  }

  @media (max-width: 992px) {
    .nav {
      display: none;
    }

    .nav-phone {
      display: flex;
    }
  }
</style>
