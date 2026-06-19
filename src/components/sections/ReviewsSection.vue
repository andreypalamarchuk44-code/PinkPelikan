<script setup>
import { ref } from 'vue'
import { IconStarFilled } from '@tabler/icons-vue'

const reviews = ref([
  {
    name: 'Олена',
    text: 'Дуже гарне місце для відпочинку. Басейн чистий, атмосфера чудова, персонал привітний.'
  },
  {
    name: 'Андрій',
    text: 'Приїжджали компанією на вихідні. Все сподобалось: кухня, музика та вечірня атмосфера.'
  },
  {
    name: 'Марина',
    text: 'Комфортні номери, смачні коктейлі та чудова територія. Обов’язково повернемося.'
  },
  {
    name: 'Віталій',
    text: 'Одне з найкращих місць у Ладижині для літнього відпочинку.'
  }
])
</script>

<template>
  <section
    id="reviews"
    class="reviews"
  >
    <div class="container">

      <div class="reviews__head">

        <span class="reviews__label">
          Відгуки гостей
        </span>

        <h2 class="reviews__title">
          Гості повертаються
          <span>знову і знову</span>
        </h2>

        <p class="reviews__text">
          Найкраще про нас розкажуть люди,
          які вже відпочивали у Pink Pelikan.
        </p>

      </div>

      <div class="reviews__grid">

        <article
          v-for="review in reviews"
          :key="review.name"
          class="review-card"
        >

          <div class="review-card__stars">
            <IconStarFilled
              v-for="star in 5"
              :key="star"
              :size="18"
            />
          </div>

          <p class="review-card__text">
            "{{ review.text }}"
          </p>

          <div class="review-card__footer">
            <strong>{{ review.name }}</strong>
          </div>

        </article>

      </div>

      <div class="reviews__stats">

        <div class="stat">
          <strong>4.9</strong>
          <span>Середній рейтинг</span>
        </div>

        <div class="stat">
          <strong>100+</strong>
          <span>Задоволених гостей</span>
        </div>

        <div class="stat">
          <strong>2024</strong>
          <span>Рік відкриття</span>
        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.reviews {
  scroll-margin-top: 100px;
  padding: 140px 0;
  background: #050505;
  position: relative;
}

.reviews__head {
  text-align: center;
  max-width: 800px;
  margin: 0 auto 70px;
}

.reviews__label {
  display: inline-block;
  margin-bottom: 14px;

  color: var(--pink);

  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: .85rem;
}

.reviews__title {
  margin: 0;

  color: white;

  font-size:
    clamp(2.5rem, 5vw, 4.8rem);

  line-height: 1.05;
}

.reviews__title span {
  display: block;
  color: var(--pink);
}

.reviews__text {
  margin-top: 24px;

  color: #9ca3af;

  line-height: 1.8;
}

.reviews__grid {
  display: grid;

  grid-template-columns:
    repeat(4, 1fr);

  gap: 24px;
}

.review-card {
  padding: 32px;

  border-radius: 30px;

  background:
    rgba(16,17,20,.85);

  border:
    1px solid rgba(255,62,168,.08);

  backdrop-filter: blur(20px);

  transition: .35s ease;
}

.review-card:hover {
  transform: translateY(-8px);

  border-color:
    rgba(255,62,168,.25);

  box-shadow:
    0 0 40px rgba(255,62,168,.12);
}

.review-card__stars {
  display: flex;
  gap: 4px;

  color: #ffb800;

  margin-bottom: 20px;
}

.review-card__text {
  color: #d1d5db;

  line-height: 1.8;

  min-height: 140px;
}

.review-card__footer {
  margin-top: 25px;

  color: white;
}

.reviews__stats {
  margin-top: 80px;

  display: grid;

  grid-template-columns:
    repeat(3, 1fr);

  gap: 24px;
}

.stat {
  padding: 30px;

  border-radius: 30px;

  text-align: center;

  background:
    rgba(16,17,20,.85);

  border:
    1px solid rgba(255,62,168,.08);
}

.stat strong {
  display: block;

  color: var(--pink);

  font-size: 3rem;
}

.stat span {
  color: #9ca3af;
}

@media (max-width: 1100px) {

  .reviews__grid {
    grid-template-columns:
      repeat(2, 1fr);
  }

  .reviews__stats {
    grid-template-columns:
      repeat(2, 1fr);
  }
}

@media (max-width: 768px) {

  .reviews {
    padding: 90px 0;
  }

  .reviews__grid,
  .reviews__stats {
    grid-template-columns: 1fr;
  }

  .review-card__text {
    min-height: auto;
  }
}
</style>