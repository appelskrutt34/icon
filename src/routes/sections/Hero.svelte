<section class="section base-container">
  <div class="section-content">
    <h1 class="title">
      YOU DONT NEED <br /> MORE
      <span style="color: var(--red)"> WILLPOWER</span>
      <br /> YOU NEED AN ICON
    </h1>
    <p class="subtitle">
      Download your favorite athlete's brain. Straight to your phone.
    </p>
    <div class="buttons">
      <button class="base-button gray-button">Complete fitness quiz</button>
      <button class="base-button red-button">Join Waitlist</button>
    </div>
    <div class="users">
      <img src="./hero-users.png" alt="" />
      <p>Trusted by 400+ <br /> individuals worldwide</p>
    </div>
  </div>
  <img src="./hero-image.png" alt="hero" class="image" />
  <div class="users-phone">
    <img src="./hero-users.png" alt="" />
    <p>Trusted by 400+ <br /> individuals worldwide</p>
  </div>
</section>

<style>
  .section {
    height: 100vh;
    display: flex;
    align-items: center;
  }
  .image {
    width: 100%;
    flex: 1 1 0%;
    object-fit: contain;
  }
  .section-content {
    width: 100%;
    flex: 1 1 0%;
    display: flex;
    flex-direction: column;
    gap: 22px;
  }
  .title {
    font-size: 64px;
  }
  .subtitle {
    color: var(--dark-white);
  }
  .buttons {
    display: flex;
    gap: 0.8em;
    align-items: center;
  }
  .users {
    margin-top: 4em;
    padding-left: 1.2em;
    display: flex;
    gap: 0.8em;
    border-left: var(--light-gray) solid 1px;
    align-items: center;
  }
  .users-phone {
    display: none;
  }

  @media (max-width: 992px) {
    .users {
      display: none;
    }
    .users-phone {
      margin-top: 2em;
      padding-left: 1.2em;
      display: flex;
      gap: 12px;
      border-left: var(--light-gray) solid 1px;
      align-items: center;
    }
    .section {
      height: 100%;
      padding-top: 98px;
      padding-bottom: 40px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .section-content {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      gap: 18px;
      text-align: center;
    }
    .title {
      font-size: 34px;
    }
  }
</style>
