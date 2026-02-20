<script>
  let reviews = [
    {
      name: "Saran Ali",
      role: "Manager, Clowd",
      comment:
        "I’ve tried every fitness app out there — they all gave me generic plans. Icon asked questions no other app ever did. It feels like my coach actually gets how my life works.",
      stars: 5.0,
      image: "./martin.png",
    },

    {
      name: "Kevin Martin",
      role: "Manager, Clowd",
      comment:
        "Before Icon, I wasted hours researching workouts and diets. Now my Icon tells me exactly what to do, and it adapts when I miss a day. Zero guilt, just progress.",
      stars: 5.0,
      image: "./martin.png",
    },
    {
      name: "Sam Waltman",
      role: "Manager, Clowd",
      comment:
        "My Icon checks in at the perfect times. When I skip workouts or don’t eat right, it gives me that friendly nudge. It’s like having a personal trainer who actually lives in your phone.",
      stars: 5.0,
      image: "./sam.png",
    },
    {
      name: "Elsa Hosk",
      role: "Manager, Clowd",
      comment:
        "Icon taught me to stop chasing perfection and focus on consistency. My coach feels human, not robotic. I’m stronger, happier, and finally confident in my skin.",
      stars: 5.0,
      image: "./elsa.png",
    },
    {
      name: "Sam Manning",
      role: "Medical Assisant",
      comment:
        "Between kids, work, and chaos — Icon keeps me on track. My plan adjusts daily based on my energy and sleep. It’s scary smart.",
      stars: 5.0,
      image: "./rachel.png",
    },
    {
      name: "Rachel Green",
      role: "Medical Assisant",
      comment:
        "I told Icon I was recovering from an injury, and it completely changed my workouts to help me heal. That kind of personalization is unreal.",
      stars: 5.0,
      image: "./rachel.png",
    },
    {
      name: "Sharon lambert",
      role: "President of Sales",
      comment:
        "Icon reminded me that my journey is mine. No filters, no fake influencers — just results. I’m proud of my progress for the first time ever",
      stars: 5.0,
      image: "./sharon.png",
    },
    {
      name: "Ted Johnson",
      role: "Dog Trainer",
      comment:
        "The AI + athlete combo is pure genius. It’s not just training — it’s education. My Icon explains why I’m doing each workout. That changed everything.",
      stars: 5.0,
      image: "./ted.png",
    },
  ];
</script>

<section class="section l-vertical-margin">
  <h1 class="section__title">
    Created by athletes, trusted <br /> by everyone
  </h1>
  <p class="section__subtitle">
    Every Icon user starts with a goal. Most never look back
  </p>

  <!-- Monitor -->
  <div class="reviews__layout">
    <div class="reviews reviews__top">
      {#each reviews.slice(0, 4) as review, i}
        <div class="review">
          <div class="review__heading">
            <img src={review.image} class="review__image" alt={review.name} />
            <p class="l-xlarge-font">{review.name}</p>
            <p class="review__role">{review.role}</p>
          </div>

          <p class="review__comment">{review.comment}</p>
          <img src="./stars.png" alt="stars" />
        </div>
      {/each}
    </div>

    <div class="reviews reviews__bottom">
      {#each reviews.slice(4, 8) as review}
        <div class="review">
          <div class="review__heading">
            <img
              src={review.image}
              alt={review.imageAltText}
              class="review__image"
            />
            <p class="l-xlarge-font">{review.name}</p>
            <p class="review__role">{review.role}</p>
          </div>

          <p class="review__comment">{review.comment}</p>
          <img src="./stars.png" alt="stars" />
        </div>
      {/each}
    </div>
    <img
      src="./blur-left.png"
      aria-hidden="true"
      alt=""
      class="image__blur__left"
    />
    <img
      src="./blur-right.png"
      aria-hidden="true"
      alt=""
      class="image__blur__right"
    />
  </div>

  <!-- Phone -->
  <div class="reviews--phone">
    {#each reviews as review}
      <div class="review">
        <div class="review__heading">
          <img
            src={review.image}
            alt={review.imageAltText}
            class="review__image"
          />
          <p class="l-xlarge-font">{review.name}</p>
          <p class="review__role">{review.role}</p>
        </div>

        <p class="review__comment">{review.comment}</p>
        <img src="./stars.png" alt="stars" />
      </div>
    {/each}
  </div>
</section>

<style>
  .section {
    text-align: center;
  }
  .reviews__layout {
    position: relative;
  }
  .image__blur__right {
    position: absolute;
    right: 0;
    object-fit: contain;
    z-index: 50;
    height: 200%;
    top: -50%;
  }
  .image__blur__left {
    position: absolute;
    left: 0;
    height: 200%;
    object-fit: contain;
    z-index: 50;
    top: -50%;
  }
  .section__subtitle {
    color: var(--light-gray);
    margin-top: 1rem;
    margin-bottom: 4rem;
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .reviews {
    width: 100%;
    display: flex;
    overflow-x: hidden;
    justify-content: flex-start;
    gap: 1rem;
  }
  .reviews__top .review:first-child {
    margin-left: -16rem;
  }
  .reviews__bottom .review:first-child {
    margin-left: -4rem;
  }
  .reviews__bottom {
    margin-top: 1rem;
  }
  .review {
    text-align: left;
    flex: 0 0 30%;
    scroll-snap-align: center;
    border-radius: 16px;
    background-color: var(--gray);
    padding: 1em;
  }
  .review__heading {
    border-bottom: solid 1px var(--medium-gray);
  }
  .review__image {
    margin-bottom: 1rem;
  }
  .review__role {
    margin-top: 0.2rem;
    margin-bottom: 0.5rem;
    color: var(--light-gray);
  }
  .review__comment {
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
  }

  .reviews--phone {
    display: none;
  }

  @media (max-width: 992px) {
    .reviews__layout {
      display: none;
    }
    .section {
      max-width: 100vw;
      overflow-x: hidden;
      margin-left: 0;
      margin-right: 0;
    }

    .reviews--phone {
      padding-left: 1rem;
      padding-right: 1rem;
      width: 100%;
      display: flex;
      overflow-x: scroll;
      scroll-snap-type: x mandatory;
      -webkit-overflow-scrolling: touch;
      scrollbar-width: none;
      justify-content: start;
      gap: 1rem;

      box-sizing: border-box;
    }

    .review {
      flex: 0 0 80%;
      max-width: 400px;
    }
  }
</style>
