<script>
</script>

<footer class="footer l-vertical-margin">
  <div class="l-container">
    <div class="footer__logo">
      <img src="./icon.png" alt="logo" />
    </div>

    <div class="footer__links__layout">
      <div class="footer__links__stores">
        <a href="#"><img src="./app-store-badge.png" alt="apple store" /> </a>
        <a href="#"><img src="./google-play-badge.png" alt="google play" /></a>
      </div>

      <div class="footer__links__socialmedia">
        <a href="#" class="socialmedia__button"
          ><img src="./icons/twitter-icon.png" alt="twitter" /></a
        >
        <a href="#" class="socialmedia__button"
          ><img src="./icons/facebook-icon.png" alt="twitter" /></a
        >
        <a href="#" class="socialmedia__button"
          ><img src="./icons/instagram-icon.png" alt="twitter" /></a
        >
        <a href="#" class="socialmedia__button"
          ><img src="./icons/linkedin-icon.png" alt="twitter" /></a
        >
      </div>
    </div>

    <div class="footer__pages__layout">
      <div class="footer__pages">
        <a href="#" class="link">Home</a>
        <a href="#" class="link">Trainers</a>
        <a href="#" class="link">Pricing</a>
        <a href="#" class="link">About Us</a>
        <a href="#" class="link">Contact Us</a>
        <a href="#" class="link">Help</a>
      </div>

      <div class="footer__links__socialmedia--phone">
        <a href="#" class="socialmedia__button"
          ><img src="./icons/twitter-icon.png" alt="twitter" /></a
        >
        <a href="#" class="socialmedia__button"
          ><img src="./icons/facebook-icon.png" alt="twitter" /></a
        >
        <a href="#" class="socialmedia__button"
          ><img src="./icons/instagram-icon.png" alt="twitter" /></a
        >
        <a href="#" class="socialmedia__button"
          ><img src="./icons/linkedin-icon.png" alt="twitter" /></a
        >
      </div>
      <div class="footer__email">
        <p>
          <span class="feedback__text">Send Your Feedback</span> : Icon@gmail.com
        </p>
      </div>
    </div>

    <div class="footer__bottom">
      <p class="footer__bottom__rights">© 2025 ICON. All rights reserved</p>
      <div class="footer__bottom__policies">
        <a href="#" class="link policy">Privacy Policy</a>
        <span>|</span>
        <a href="#" class="link policy">Terms & Condition</a>
        <span>|</span>
        <a href="#" class="link policy">Cookie Notice</a>

        <a href="#" class="link policy">Copyright Policy</a>
        <span>|</span>
        <a href="#" class="link policy">Data Policy</a>
      </div>
    </div>

    <div class="footer__bottom--phone">
      <div>
        <a href="#" class="link policy">Privacy Policy</a>
        <span>|</span>
        <a href="#" class="link policy">Terms & Condition</a>
        <span>|</span>
        <a href="#" class="link policy">Cookie Notice</a>
      </div>
      <div>
        <a href="#" class="link policy">Copyright Policy</a>
        <span>|</span>
        <a href="#" class="link policy">Data Policy</a>
      </div>
      <p class="footer__bottom__rights--phone">
        © 2025 ICON. All rights reserved
      </p>
    </div>
  </div>
</footer>

<style>
  .footer {
    width: 100%;
  }
  .footer__links__layout {
    display: flex;
    justify-content: space-between;
    margin-top: 1rem;
    margin-bottom: 2rem;
  }
  .footer__pages__layout {
    display: flex;
    justify-content: space-between;
    margin-bottom: 2rem;
  }

  .footer__pages {
    display: flex;
    gap: 2rem;
  }
  .footer__links__stores {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  .footer__links__socialmedia {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  .logo__layout {
    display: flex;
    justify-content: start;
  }
  .link {
    transition: color 0.3s ease;
  }
  .link:hover {
    color: var(--red);
  }
  .socialmedia__button {
    position: relative;
    padding: 1rem;
    border-radius: 50px;
    background-color: var(--gray);
    transition: border 0.3s ease;
    display: flex;
    align-items: center;
    text-align: left;
  }
  .socialmedia__button::before {
    content: "";
    position: absolute;
    inset: 0;
    padding: 2px;
    border-radius: 50px;
    background: linear-gradient(90deg, var(--blue), var(--red), var(--blue));
    background-size: 200% 200%;
    opacity: 0;
    transition: opacity 0.3s ease;
    -webkit-mask:
      linear-gradient(#fff 0 0) content-box,
      linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    pointer-events: none;
    z-index: 0;
  }
  .feedback__text {
    color: var(--light-gray);
  }
  .socialmedia__button:hover::before {
    opacity: 1;
  }
  .footer__bottom {
    display: flex;
    justify-content: space-between;
    border-top: solid 1px var(--medium-gray);
    padding-top: 1rem;
    color: var(--light-gray);
  }
  .footer__bottom__policies {
    display: flex;
    gap: 1rem;
  }
  .policy {
    color: var(--light-gray);
  }
  .footer__links__socialmedia--phone {
    display: none;
  }
  .footer__bottom__rights--phone {
    display: none;
  }
  .footer__bottom--phone {
    display: none;
  }

  @media (max-width: 992px) {
    .footer__links__socialmedia {
      display: none;
    }
    .footer__bottom {
      display: none;
    }
    .footer__bottom__rights--phone {
      display: block;
    }
    .footer__bottom {
      flex-direction: column;
      gap: 1.5rem;
    }
    .footer__links__layout {
      flex-direction: column;
      gap: 1rem;
    }
    .footer__pages {
      gap: 0.8rem;
    }

    .footer__links__socialmedia--phone {
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .footer__pages__layout {
      flex-direction: column;
      gap: 1.5rem;
    }
    .footer__bottom__policies {
      display: grid;
      grid-template-columns: repeat(5, min-content);
      justify-content: start;
    }
    .footer__bottom--phone {
      display: flex;
      flex-direction: column;
      gap: 0.2rem;
      border-top: solid 1px var(--medium-gray);
      padding-top: 1rem;
      color: var(--light-gray);
    }
    .footer__bottom__rights--phone {
      margin-top: 1rem;
    }
  }
</style>
