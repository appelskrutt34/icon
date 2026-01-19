<script>
  import { fade, scale, slide } from "svelte/transition";
  import Close from "./icons/Close.svelte";
  import Menu from "./icons/Menu.svelte";

  let openPhoneMenu = $state(false);
</script>

<div class="nav">
  <!-- Monitor -->
  <nav class="nav__layout l-container">
    <a aria-label="Home" href="#" class="link"
      ><img src="./icon.png" alt="logo" /></a
    >
    <div class="nav__pages">
      <a href="#" class="link">Home</a>
      <a href="#" class="link">Trainers</a>
      <a href="#" class="link">Pricing</a>
      <a href="#" class="link">About Us</a>
      <a href="#" class="link">Contact Us</a>
    </div>
    <button class="link">Join Waitlist</button>
  </nav>

  <!-- Phone -->
  <nav class="nav__layout--phone l-container">
    <div class="nav__icons--phone">
      <a aria-label="Home" href="#"><img src="./icon.png" alt="logo" /></a>
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
      <div in:slide out:slide class="nav__pages--phone">
        <a href="#">Home</a>
        <a href="#">Trainers</a>
        <a href="#">Pricing</a>
        <a href="#">About Us</a>
        <a href="#">Contact Us</a>
      </div>
    {/if}
  </nav>
</div>

<style>
  .nav {
    display: flex;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 50;
    color: var(--white);
    border-bottom: 1px solid var(--medium-gray);
    padding-top: 16px;
    padding-bottom: 16px;
    background-color: rgba(var(--black), var(--black), var(--black), 0.3);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
  }

  .nav__pages {
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

  .nav__layout {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nav__layout--phone {
    display: none;
  }

  @media (max-width: 992px) {
    .nav__layout {
      display: none;
    }

    .nav__layout--phone {
      width: 100%;
      display: flex;
      flex-direction: column;
    }

    .nav__icons--phone {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .nav__pages--phone {
      background-color: rgba(var(--black), var(--black), var(--black), 0.3);
      backdrop-filter: blur(10px);
      display: flex;
      flex-direction: column;
      gap: 18px;
      transition: all 0.3s ease;
      padding-top: 26px;
    }
  }
</style>
