<script setup>
import {
  IconMusic,
  IconMicrophone2,
  IconConfetti,
  IconStars
} from '@tabler/icons-vue'

const heroVideo = new URL('@/assets/video/disco.mp4', import.meta.url).href

const events = [
  {
    icon: IconMusic,
    title: 'DJ Night',
    text: 'Сучасна музика, коктейлі та атмосфера літньої ночі.'
  },
  {
    icon: IconMicrophone2,
    title: 'Live Music',
    text: 'Живі виступи та вечори під відкритим небом.'
  },
  {
    icon: IconConfetti,
    title: 'Private Events',
    text: 'Дні народження, корпоративи та святкові події.'
  },
  {
    icon: IconStars,
    title: 'Pool Party',
    text: 'Найяскравіші літні вечірки біля басейну.'
  }
]
</script>

<template>
  <section id="events" class="events">

    <div class="container">

      <!-- TOP -->
      <div class="events__top">
        <span class="events__label">Події та атмосфера</span>

        <h2 class="events__title">
          Коли сонце заходить,
          <span>Pink Pelikan оживає</span>
        </h2>

        <p class="events__text">
          Музика, коктейлі, басейн та вечірня атмосфера —
          усе для незабутнього відпочинку.
        </p>
      </div>

      <!-- GRID -->
      <div class="events__grid">
        <article
          v-for="event in events"
          :key="event.title"
          class="event-card"
        >
          <component
            :is="event.icon"
            :size="42"
            class="event-card__icon"
          />

          <h3>{{ event.title }}</h3>
          <p>{{ event.text }}</p>
        </article>
      </div>

      <!-- BANNER -->
      <div class="events__banner">

        <video
          class="events__video"
          autoplay
          muted
          loop
          playsinline
        >
          <source :src="heroVideo" type="video/mp4">
        </video>

        <div class="events__overlay"></div>

        <div class="events__content">
          <span>Summer Vibes</span>

          <h3>
            Відпочивай вдень —<br />
            танцюй вночі
          </h3>

          <a href="#contacts" class="events__btn">
            Забронювати столик
          </a>
        </div>

      </div>

    </div>

  </section>
</template>

<style scoped>
.events {
  scroll-margin-top: 100px;
  padding: 140px 0;
  background: #050505;
}

/* TOP */
.events__top {
  text-align: center;
  max-width: 900px;
  margin: 0 auto 80px;
}

.events__label {
  color: var(--pink);
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 0.85rem;
}

.events__title {
  color: white;
  font-size: clamp(2.6rem, 5vw, 4.8rem);
  line-height: 1.05;
}

.events__title span {
  color: var(--pink);
}

.events__text {
  margin-top: 20px;
  color: #9ca3af;
  line-height: 1.7;
  max-width: 700px;
  margin-inline: auto;
}

/* GRID */
.events__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
  margin-bottom: 80px;
}

.event-card {
  padding: 30px;
  border-radius: 28px;
  background: rgba(16, 17, 20, 0.85);
  border: 1px solid rgba(255, 62, 168, 0.08);
  transition: 0.3s ease;
}

.event-card:hover {
  transform: translateY(-6px);
  border-color: rgba(255, 62, 168, 0.25);
}

.event-card__icon {
  color: var(--pink);
  margin-bottom: 18px;
}

.event-card h3 {
  color: white;
  margin-bottom: 10px;
}

.event-card p {
  color: #9ca3af;
  line-height: 1.6;
}

/* BANNER */
.events__banner {
  position: relative;
  height: 550px;
  border-radius: 36px;
  overflow: hidden;
  border: 1px solid rgba(255, 62, 168, 0.15);
}

/* VIDEO */
.events__video {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  z-index: 0;
}

/* OVERLAY */
.events__overlay {
  position: absolute;
  inset: 0;
  z-index: 1;
  background: linear-gradient(
    90deg,
    rgba(0, 0, 0, 0.85),
    rgba(0, 0, 0, 0.4),
    rgba(0, 0, 0, 0.1)
  );
}

/* CONTENT */
.events__content {
  position: absolute;
  top: 50%;
  left: 70px;
  transform: translateY(-50%);
  z-index: 2;
  max-width: 550px;
}

.events__content span {
  color: var(--pink);
  text-transform: uppercase;
  letter-spacing: 2px;
}

.events__content h3 {
  margin: 18px 0;
  color: white;
  font-size: clamp(2rem, 4vw, 3.5rem);
  line-height: 1.1;
}

.events__btn {
  display: inline-flex;
  padding: 16px 32px;
  border-radius: 999px;
  background: linear-gradient(135deg, #ff3ea8, #ff6dc3);
  color: white;
  font-weight: 700;
  text-decoration: none;
  box-shadow: 0 0 30px rgba(255, 62, 168, 0.25);
}

/* RESPONSIVE */
@media (max-width: 1100px) {
  .events__grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .events {
    padding: 90px 0;
  }

  .events__grid {
    grid-template-columns: 1fr;
  }

  .events__banner {
    height: 420px;
  }

  .events__content {
    left: 20px;
    right: 20px;
    text-align: center;
  }
}

@media (max-width: 480px) {
  .events__banner {
    height: 320px;
  }

  .events__content {
    left: 16px;
    right: 16px;
  }

  .events__content h3 {
    font-size: 1.6rem;
  }

  .events__btn {
    padding: 13px 24px;
    font-size: .9rem;
  }
}
</style>