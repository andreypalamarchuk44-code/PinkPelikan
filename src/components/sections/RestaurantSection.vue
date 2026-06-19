<script setup>
import { ref } from 'vue'

const activeCategory = ref('cocktails')

const categories = [
  { id: 'cocktails', label: '🍹 Коктейлі' },
  { id: 'shots', label: '🥃 Шоти' },
  { id: 'soft', label: '🥤 Безалкогольні' },
  { id: 'snacks', label: '🍢 Закуски' },
  { id: 'hookah', label: '💨 Кальяни' }
]

const menu = {
  cocktails: [
    { name: 'Pink Pelikan', desc: 'Джин, малиновий лікер, тонік, лимон, м\'ята', price: '145 ₴', badge: 'Хіт' },
    { name: 'Flamingo Sunset', desc: 'Текіла, грейпфрут, апельсин', price: '155 ₴', badge: '' },
    { name: 'Mojito Classic', desc: 'Ром, лайм, м\'ята, сода', price: '130 ₴', badge: '' }
  ],

  shots: [
    { name: 'B-52', desc: 'Kahlua, Bailey\'s, Grand Marnier', price: '85 ₴', badge: '' },
    { name: 'Tequila Boom', desc: 'Текіла + тонік', price: '65 ₴', badge: '' }
  ],

  soft: [
    { name: 'Лимонад Pink', desc: 'Малина, лимон, м\'ята', price: '85 ₴', badge: 'Хіт' },
    { name: 'Огірок-лайм', desc: 'Огірок, лайм, сода', price: '80 ₴', badge: '' }
  ],

  snacks: [
    { name: 'Нагетси', desc: '8 шт., соус BBQ', price: '120 ₴', badge: '' },
    { name: 'Фрі з трюфелем', desc: 'Пармезан, трюфельна олія', price: '115 ₴', badge: 'Топ' }
  ],

  hookah: [
    { name: 'Blueberry Mint', desc: 'Чорниця + м’ята', price: '300 ₴', badge: 'Хіт' },
    { name: 'Watermelon Chill', desc: 'Кавун + холодна м’ята', price: '320 ₴', badge: '' },
    { name: 'Tropical Mix', desc: 'Манго + ананас + маракуя', price: '340 ₴', badge: '' },
    { name: 'Double Apple', desc: 'Класичне яблуко', price: '280 ₴', badge: '' },
    { name: 'Berry Explosion', desc: 'Малина + ожина + смородина', price: '330 ₴', badge: 'Новинка' }
  ]
}
</script>

<template>
  <section id="restaurant" class="restaurant">
    <div class="container">

      <div class="restaurant__head">
        <span class="restaurant__label">Кухня & Бар</span>
        <h2 class="restaurant__title">
          Смак, який хочеться
          <span>повторити</span>
        </h2>
        <p class="restaurant__sub">
          Від легких закусок до повноцінної вечері.
          Наш бар та кухня створені для того,
          щоб кожен момент відпочинку був особливим.
        </p>
      </div>

      <!-- CATEGORY TABS -->
      <div class="menu-tabs" role="tablist">
        <button
          v-for="cat in categories"
          :key="cat.id"
          class="menu-tab"
          :class="{ 'menu-tab--active': activeCategory === cat.id }"
          @click="activeCategory = cat.id"
          role="tab"
          :aria-selected="activeCategory === cat.id"
        >
          {{ cat.label }}
        </button>
      </div>

      <!-- MENU GRID -->
      <div class="menu-grid">
        <div
          v-for="item in menu[activeCategory]"
          :key="item.name"
          class="menu-card"
        >
          <div class="menu-card__top">
            <h3 class="menu-card__name">{{ item.name }}</h3>
            <span v-if="item.badge" class="menu-card__badge">{{ item.badge }}</span>
          </div>
          <p class="menu-card__desc">{{ item.desc }}</p>
          <div class="menu-card__price">{{ item.price }}</div>
        </div>
      </div>

      <!-- RESTAURANT IMAGE + CTA -->
      <div class="restaurant__bottom">
        <div class="restaurant__image">
          <img src="@/assets/images/bar.jpg" alt="Бар Pink Pelikan" />
          <div class="restaurant__img-overlay">
            <span>Pink Pelikan Bar</span>
          </div>
        </div>
        <div class="restaurant__cta">
          <h3>Замовити столик</h3>
          <p>Зателефонуйте або напишіть нам у Telegram — ми забронюємо для вас найкраще місце біля басейну або в барі.</p>
          <div class="restaurant__cta-btns">
            <a href="https://t.me/pink_pelikan_bot" target="_blank" rel="noopener" class="cta-btn cta-btn--tg">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.562 8.248-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.26 14.4l-2.95-.924c-.64-.204-.654-.64.136-.95l11.527-4.448c.533-.194 1 .131.59.17z"/></svg>
              Написати в Telegram
            </a>
            <a href="tel:+380974587955" class="cta-btn cta-btn--call">
              📞 Зателефонувати
            </a>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.restaurant {
  scroll-margin-top: 100px;
  padding: 140px 0;
  background: #09090d;
}

.restaurant__head {
  text-align: center;
  margin-bottom: 60px;
}

.restaurant__label {
  color: var(--pink);
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: .85rem;
}

.restaurant__title {
  margin-top: 20px;
  color: #fff;
  font-size: clamp(2.2rem, 5vw, 4.5rem);
  line-height: 1.1;
}

.restaurant__title span { color: var(--pink); }

.restaurant__sub {
  margin-top: 20px;
  color: #9ca3af;
  max-width: 560px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.8;
}

/* TABS */
.menu-tabs {
  display: flex;
  gap: 12px;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 48px;
}

.menu-tab {
  padding: 12px 24px;
  border-radius: 999px;
  border: 1px solid rgba(255,62,168,.2);
  background: transparent;
  color: #9ca3af;
  font-size: .95rem;
  font-weight: 500;
  cursor: pointer;
  transition: .3s;
  font-family: inherit;
}

.menu-tab:hover {
  border-color: var(--pink);
  color: white;
}

.menu-tab--active {
  background: linear-gradient(135deg, #ff3ea8, #ff63c3);
  border-color: transparent;
  color: white;
  box-shadow: 0 0 20px rgba(255,62,168,.35);
}

/* MENU GRID */
.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
  margin-bottom: 80px;
}

.menu-card {
  padding: 24px;
  border-radius: 24px;
  background: #101114;
  border: 1px solid rgba(255,62,168,.08);
  transition: border-color .3s, transform .3s;
}

.menu-card:hover {
  border-color: rgba(255,62,168,.25);
  transform: translateY(-3px);
}

.menu-card__top {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 8px;
  margin-bottom: 10px;
}

.menu-card__name {
  color: #fff;
  font-size: 1rem;
  font-weight: 600;
  margin: 0;
  line-height: 1.3;
}

.menu-card__badge {
  flex-shrink: 0;
  padding: 3px 10px;
  border-radius: 999px;
  background: rgba(255,62,168,.15);
  color: var(--pink);
  font-size: .75rem;
  font-weight: 600;
  border: 1px solid rgba(255,62,168,.2);
}

.menu-card__desc {
  color: #6b7280;
  font-size: .88rem;
  line-height: 1.6;
  margin: 0 0 16px;
}

.menu-card__price {
  color: var(--pink);
  font-size: 1.2rem;
  font-weight: 700;
}

/* BOTTOM */
.restaurant__bottom {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.restaurant__image {
  position: relative;
  overflow: hidden;
  border-radius: 32px;
  height: 500px;
}

.restaurant__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: .6s;
}

.restaurant__image:hover img { transform: scale(1.05); }

.restaurant__img-overlay {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  padding: 30px;
  background: linear-gradient(to top, rgba(0,0,0,.8), transparent);
}

.restaurant__img-overlay span {
  color: white;
  font-weight: 600;
  font-size: 1.1rem;
}

.restaurant__cta h3 {
  color: white;
  font-size: clamp(1.8rem, 4vw, 2.8rem);
  margin-bottom: 20px;
}

.restaurant__cta p {
  color: #9ca3af;
  line-height: 1.8;
  margin-bottom: 36px;
}

.restaurant__cta-btns {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.cta-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 16px 28px;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  transition: .3s;
}

.cta-btn--tg {
  color: white;
  background: linear-gradient(135deg, #ff3ea8, #ff63c3);
  box-shadow: 0 0 25px rgba(255,62,168,.3);
}

.cta-btn--tg:hover {
  transform: translateY(-2px);
  box-shadow: 0 0 40px rgba(255,62,168,.5);
}

.cta-btn--call {
  color: white;
  border: 1px solid rgba(255,255,255,.15);
  background: rgba(255,255,255,.05);
  backdrop-filter: blur(10px);
}

.cta-btn--call:hover {
  border-color: var(--pink);
}

@media (max-width: 992px) {
  .restaurant__bottom {
    grid-template-columns: 1fr;
  }

  .restaurant__image {
    height: 360px;
  }
}

@media (max-width: 768px) {
  .restaurant { padding: 80px 0; }

  .menu-grid {
    grid-template-columns: 1fr;
  }

  .menu-tabs {
    gap: 8px;
  }

  .menu-tab {
    padding: 10px 18px;
    font-size: .85rem;
  }
}

@media (max-width: 480px) {
  .restaurant__image { height: 280px; }
}
</style>
