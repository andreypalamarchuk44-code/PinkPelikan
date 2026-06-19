<script setup>
import poolImg from '@/assets/images/pool.jpg'
import hotelImg from '@/assets/images/hotel.jpg'
import barImg from '@/assets/images/bar.jpg'
import kitchenImg from '@/assets/images/kitchen.jpg'
import djImg from '@/assets/images/dj.jpg'
import eventsImg from '@/assets/images/events.jpg'

const features = [
  {
    image: poolImg,
    title: 'Басейн',
    text: 'Великий басейн із комфортною зоною відпочинку.'
  },
  {
    image: hotelImg,
    title: 'Готель',
    text: 'Затишні номери для комфортного проживання.'
  },
  {
    image: barImg,
    title: 'Бар',
    text: 'Авторські коктейлі та прохолодні напої.'
  },
  {
    image: kitchenImg,
    title: 'Кухня',
    text: 'Страви української та європейської кухні.'
  },
  {
    image: djImg,
    title: 'DJ Party',
    text: 'Вечірки, музика та атмосфера літа.'
  },
  {
    image: eventsImg,
    title: 'Кальяни',
    text: 'Преміальні кальяни від 300 грн.'
  }
]
</script>

<template>
  <section id="features" class="features">
    <div class="container">

      <div class="section-head">
        <span class="section-label">Pink Pelikan</span>

        <h2 class="section-title">
          У нас є все для <span>твого відпочинку</span>
        </h2>
      </div>

      <div class="features-grid">

        <article
          v-for="item in features"
          :key="item.title"
          class="feature-card"
        >

          <img
            :src="item.image"
            :alt="item.title"
            class="feature-image"
          />

          <div class="overlay"></div>

          <div class="content">
            <h3>{{ item.title }}</h3>
            <p>{{ item.text }}</p>
          </div>

        </article>

      </div>

    </div>
  </section>
</template>

<style scoped>
.features {
  padding: 120px 0;
  background: linear-gradient(to bottom, #050505, #0b0b10);
  scroll-margin-top: 90px;
}

.section-head {
  text-align: center;
  margin-bottom: 70px;
}

.section-label {
  color: var(--pink);
  letter-spacing: 2px;
  text-transform: uppercase;
  font-size: 0.85rem;
}

.section-title {
  margin-top: 14px;
  color: white;
  font-size: clamp(2rem, 4vw, 3.6rem);
  font-weight: 800;
}

.section-title span {
  color: var(--pink);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.feature-card {
  position: relative;
  height: 320px;
  border-radius: 28px;
  overflow: hidden;
  cursor: pointer;
}

.feature-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: 0.6s ease;
}

.overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(0,0,0,0.85),
    rgba(0,0,0,0.25),
    rgba(0,0,0,0.05)
  );
  z-index: 1;
}

.content {
  position: absolute;
  bottom: 22px;
  left: 22px;
  right: 22px;
  z-index: 2;

  padding: 16px 18px;
  border-radius: 18px;

  background: rgba(15, 15, 18, 0.45);
  backdrop-filter: blur(10px);

  border: 1px solid rgba(255, 62, 168, 0.15);
}

.content h3 {
  margin: 0 0 6px;
  color: white;
  font-size: 1.3rem;
}

.content p {
  margin: 0;
  color: #c4c4cc;
  font-size: 0.95rem;
  line-height: 1.5;
}

.feature-card:hover .feature-image {
  transform: scale(1.08);
}

@media (max-width: 992px) {
  .features-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .features {
    padding: 80px 0;
  }

  .features-grid {
    grid-template-columns: 1fr;
  }

  .feature-card {
    height: 260px;
  }
}
</style>