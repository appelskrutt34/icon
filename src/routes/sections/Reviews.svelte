<script>
  let reviews = [
    {
      name: "Kevin Martin",
      role: "Manager, Clowd",
      comment:
        "Before Icon, I wasted hours researching workouts and diets. Now my Icon tells me exactly what to do, and it adapts when I miss a day. Zero guilt, just progress.”",
      stars: 5.0,
      image: "./martin.png",
    },
    {
      name: "Sam Waltman",
      role: "Manager, Clowd",
      comment:
        "My Icon checks in at the perfect times. When I skip workouts or don’t eat right, it gives me that friendly nudge. It’s like having a personal trainer who actually lives in your phone.”",
      stars: 5.0,
      image: "./sam.png",
    },
    {
      name: "Elsa Hosk",
      role: "Manager, Clowd",
      comment:
        "Icon taught me to stop chasing perfection and focus on consistency. My coach feels human, not robotic. I’m stronger, happier, and finally confident in my skin.”",
      stars: 5.0,
      image: "./elsa.png",
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
        "Icon reminded me that my journey is mine. No filters, no fake influencers — just results. I’m proud of my progress for the first time ever”",
      stars: 5.0,
      image: "./sharon.png",
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

  <div class="reviews">
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
  .section__subtitle {
    color: var(--dark-white);
    margin-top: 1em;
    margin-bottom: 4em;
  }
  .reviews {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    -webkit-overflow-scrolling: touch;
    justify-content: flex-start;
    gap: 1em;
    padding-left: 1em;
    padding-right: 1em;
    box-sizing: border-box;
  }

  .review {
    text-align: left;
    max-width: 500px;
    flex: 0 0 80%;
    scroll-snap-align: center;
    border-radius: 16px;
    background-color: var(--gray);
    padding: 1em;
  }
  .review__heading {
    border-bottom: solid 1px var(--light-gray);
  }
  .review__image {
    margin-bottom: 1em;
  }
  .review__role {
    margin-top: 0.2em;
    margin-bottom: 0.5em;
    color: var(--dark-white);
  }
  .review__comment {
    margin-top: 1.5em;
    margin-bottom: 1.5em;
  }
</style>
