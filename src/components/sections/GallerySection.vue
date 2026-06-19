<script setup>
const events = [
  {
    image: new URL('@/assets/images/poster1.jpg', import.meta.url).href,
    date: '12 Липня',
    title: 'Pool Party'
  },
  {
    image: new URL('@/assets/images/poster2.jpg', import.meta.url).href,
    date: '19 Липня',
    title: 'DJ Night'
  },
  {
    image: new URL('@/assets/images/poster3.jpg', import.meta.url).href,
    date: '26 Липня',
    title: 'Summer Vibes'
  },
  {
    image: new URL('@/assets/images/poster4.jpg', import.meta.url).href,
    date: '02 Серпня',
    title: 'White Party'
  }
]
</script>

<template>
  <section
    id="gallery"
    class="gallery"
  >
    <div class="container">

      <div class="gallery__head">

        <span class="gallery__label">
          Афіша
        </span>

        <h2 class="gallery__title">
          Найближчі
          <span>події та вечірки</span>
        </h2>

        <p class="gallery__text">
          Слідкуйте за найгарячішими подіями,
          вечірками та special events у Pink Pelikan.
        </p>

      </div>

      <div class="poster-grid">

        <article
          v-for="(event, index) in events"
          :key="index"
          class="poster-card"
        >
          <img
            :src="event.image"
            :alt="event.title"
          >

          <div class="poster-card__overlay">

            <span class="poster-card__date">
              {{ event.date }}
            </span>

            <h3>
              {{ event.title }}
            </h3>

          </div>

        </article>

      </div>

    </div>
  </section>
</template>

<style scoped>
.gallery {
  scroll-margin-top: 100px;
  padding: 140px 0;
  background: #070709;
}

.gallery__head {
  text-align: center;
  max-width: 850px;
  margin: 0 auto 70px;
}

.gallery__label {
  display: inline-block;

  margin-bottom: 14px;

  color: var(--pink);

  text-transform: uppercase;
  letter-spacing: 2px;

  font-size: .85rem;
}

.gallery__title {
  margin: 0;

  color: white;

  font-size: clamp(2.6rem, 5vw, 4.8rem);

  line-height: 1.05;
}

.gallery__title span {
  color: var(--pink);
}

.gallery__text {
  margin-top: 24px;

  color: #9ca3af;

  line-height: 1.8;
}

.poster-grid {
  display: grid;

  grid-template-columns:
    repeat(4, 1fr);

  gap: 30px;
}

.poster-card {
  position: relative;

  overflow: hidden;

  border-radius: 30px;

  aspect-ratio: 3 / 4;

  background: #111;

  border:
    1px solid rgba(255,62,168,.12);

  transition: .35s ease;
}

.poster-card:hover {
  transform: translateY(-10px);

  box-shadow:
    0 20px 50px rgba(255,62,168,.15);
}

.poster-card img {
  width: 100%;
  height: 100%;

  object-fit: cover;

  transition: .8s ease;
}

.poster-card:hover img {
  transform: scale(1.08);
}

.poster-card__overlay {
  position: absolute;
  inset: 0;

  display: flex;
  flex-direction: column;
  justify-content: flex-end;

  padding: 24px;

  background:
    linear-gradient(
      to top,
      rgba(0,0,0,.95),
      rgba(0,0,0,.35),
      transparent
    );
}

.poster-card__date {
  width: fit-content;

  padding: 8px 14px;

  border-radius: 999px;

  background: var(--pink);

  color: white;

  font-size: .85rem;
  font-weight: 600;

  margin-bottom: 14px;
}

.poster-card h3 {
  margin: 0;

  color: white;

  font-size: 1.5rem;
  font-weight: 700;
}

@media (max-width: 1200px) {

  .poster-grid {
    grid-template-columns:
      repeat(2, 1fr);
  }

}

@media (max-width: 768px) {

  .gallery {
    padding: 90px 0;
  }

  .poster-grid {
    grid-template-columns: 1fr;
  }

  .gallery__title {
    font-size: 2.3rem;
  }

}
</style>