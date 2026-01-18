<section class="section l-container">
  <div class="section__content">
    <h1 class="section__title">
      YOU DONT NEED <br /> MORE
      <span style="color: var(--red)"> WILLPOWER</span>
      <br /> YOU NEED AN ICON
    </h1>
    <p class="section__subtitle">
      Download your favorite athlete's brain. Straight to your phone.
    </p>
    <div class="section__buttons">
      <button class="l-button l-gray-button">Complete fitness quiz</button>
      <button class="l-button l-red-button">Join Waitlist</button>
    </div>
    <div class="section__users">
      <img src="./hero-users.png" alt="individuals" />
      <p>Trusted by 400+ <br /> individuals worldwide</p>
    </div>
  </div>
  <img src="./hero-image.png" alt="hero" class="section__image" />
  <div class="section__users--phone">
    <img src="./hero-users.png" alt="individuals" />
    <p>Trusted by 400+ <br /> individuals worldwide</p>
  </div>
</section>

<style>
  .section {
    height: 100vh;
    display: flex;
    align-items: center;
  }
  .section__image {
    width: 100%;
    flex: 1 1 0%;
    object-fit: contain;
  }
  .section__content {
    width: 100%;
    flex: 1 1 0%;
    display: flex;
    flex-direction: column;
    gap: 22px;
  }
  .section__title {
    font-size: 48px;
  }
  .section__subtitle {
    color: var(--light-gray);
  }
  .section__buttons {
    display: flex;
    gap: 0.8rem;
    align-items: center;
  }
  .section__users {
    margin-top: 4rem;
    padding-left: 1.2rem;
    display: flex;
    gap: 0.8rem;
    border-left: var(--medium-gray) solid 1px;
    align-items: center;
  }
  .section__users--phone {
    display: none;
  }

  @media (max-width: 992px) {
    .section__users {
      display: none;
    }
    .section__users--phone {
      margin-top: 2rem;
      padding-left: 1.2rem;
      display: flex;
      gap: 12px;
      border-left: var(--medium-gray) solid 1px;
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
    .section__content {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      gap: 18px;
      text-align: center;
    }
    .section__title {
      font-size: 34px;
    }
  }
</style>
