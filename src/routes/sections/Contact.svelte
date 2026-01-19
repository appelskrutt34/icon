<section class="section l-vertical-margin">
  <div class="section__layout l-container">
    <div class="contact__header">
      <h1>Contact Us</h1>
      <p class="contact_text l-medium-font">
        We’d love to hear from you. Whether you’re a prospective user, trainer,
        or partner, drop us a line and we’ll get back to you.
      </p>
      <div class="contact__info">
        <p class="l-small-font contact__info__text">
          <img src="./phone-icon.png" alt="phone" /> +447539 994 589
        </p>
        <p class="l-small-font contact__info__text">
          <img src="./mail-icon.png" alt="mail" /> contact@icontraininq.app
        </p>
      </div>
    </div>
    <div class="contact__form">
      <label for="name" class="contact__form__label">Name</label>
      <input type="text" id="name" class="contact__form__input" />

      <label for="email" class="contact__form__label">Email</label>
      <input type="email" id="email" class="contact__form__input" />

      <label for="phone" class="contact__form__label">Phone</label>
      <input type="text" id="phone" class="contact__form__input" />

      <label for="reason" class="contact__form__label"
        >Reason for contacting us</label
      >
      <textarea id="reason" class="contact__form__input"></textarea>
      <button class="l-button l-red-button">Send Message</button>
    </div>
  </div>
</section>

<style>
  .section {
    width: 100%;
  }
  .section__layout {
    display: flex;
    align-items: center;
    gap: 3rem;
  }
  .contact__header {
    display: flex;
    flex-direction: column;
    justify-content: end;
    height: 500px;
    padding-left: 2rem;
    padding-right: 2rem;
    padding-top: 4rem;
    padding-bottom: 4rem;
    border-radius: 16px;
    background: linear-gradient(to top, var(--gray), var(--black));
    width: 100%;
  }
  .contact_text {
    margin-top: 2rem;
    margin-bottom: 2rem;
    color: var(--light-gray);
  }
  .contact__form {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  .contact__info {
    display: flex;
    align-items: center;
    gap: 2rem;
  }
  .contact__info__text {
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }
  .contact__form__label {
    margin-bottom: 0.5rem;
  }

  .contact__form__input {
    background-color: var(--gray);
    border-radius: 12px;
    padding: 1.2rem;
    border: none;
    color: var(--white);
    margin-bottom: 1.5rem;
  }

  @media (max-width: 992px) {
    .section__layout {
      flex-direction: column;
    }

    .contact__header {
      width: auto;
      margin: -1rem !important;
    }
  }
</style>
