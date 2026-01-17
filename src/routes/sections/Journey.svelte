<section class="section l-container l-vertical-margin">
  <div class="stats">
    <div>
      <p class="l-xxxlarge-font">4.9</p>
      <p class="l-xmedium-font stats__text">App store Rating</p>
    </div>
    <div>
      <p class="l-xxxlarge-font">92%</p>
      <p class="l-xmedium-font stats__text">Goal Succcess Rate</p>
    </div>
    <div>
      <p class="l-xxxlarge-font">120k+</p>
      <p class="l-xmedium-font stats__text">Workouts Logged</p>
    </div>
    <div>
      <p class="l-xxxlarge-font">100k+</p>
      <p class="l-xmedium-font stats__text">Active Users Worldwide</p>
    </div>
  </div>

  <div class="journey l-vertical-margin">
    <div class="journey__heading">
      <h1 class="journey__title">
        Ready to take control of <br /> your fitness yourney?
      </h1>
      <h1 class="journey__title--phone">
        Ready to take control <br />of your fitness <br /> yourney?
      </h1>
      <p class="l-medium-font journey__subtitle">
        Join the waitlist and be part of the <br /> future of personal training.
      </p>
    </div>

    <div class="journey__body">
      <div class="journey__box">
        <p class="l-large-font">Join Waitlist</p>
        <p class="journey__box__text">
          Help us build the most iconic fitness app in the world
        </p>
        <button class="l-button l-red-button journey__box__button"
          >Join Waitlist</button
        >
      </div>

      <div class="journey__box">
        <p class="l-large-font">Complete fitness quiz</p>
        <p class="journey__box__text">
          Find out exactly what your body was made to do, and how to do it
        </p>
        <button class="l-button l-red-button journey__box__button"
          >Complete fitness quiz</button
        >
      </div>
    </div>
  </div>
</section>

<style>
  .section {
    width: 100%;
  }
  .stats {
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
  .stats__text {
    margin-top: 0.5rem;
    color: var(--light-gray);
  }

  .journey {
    background: linear-gradient(to bottom, var(--gray), var(--black));
    border-radius: 16px;
    padding: 2rem;
  }
  .journey__heading {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    margin-top: 4rem;
    margin-bottom: 4rem;
  }
  .journey__subtitle {
    color: var(--light-gray);
  }
  .journey__body {
    width: 100%;
    display: flex;
    gap: 2rem;
  }
  .journey__box {
    background-color: var(--black);
    display: flex;
    align-items: center;
    flex-direction: column;
    border-radius: 16px;
    padding: 2rem;
    width: 100%;
  }
  .journey__box__text {
    margin-top: 1rem;
    margin-bottom: 4rem;
    color: var(--light-gray);
  }
  .journey__box__button {
    width: 100%;
  }
  .journey__title--phone {
    display: none;
  }

  @media (max-width: 992px) {
    .journey__title {
      display: none;
    }
    .journey__title--phone {
      display: inline;
    }
    .journey__heading {
      flex-direction: column;
      justify-content: center;
      text-align: center;
      gap: 1rem;
    }
    .journey__body {
      flex-direction: column;
    }
    .journey__box {
      width: auto;
    }
    .stats {
      display: grid;
      grid-template-columns: repeat(2, auto);
    }
  }
</style>
