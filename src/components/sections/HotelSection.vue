<script setup>
</script>

<template>
  <section
    id="hotel"
    class="hotel"
  >
    <div class="container">

      <div class="hotel__grid">

        <!-- LEFT -->
        <div class="hotel__content">

          <span class="hotel__label">
            Готель
          </span>

          <h2 class="hotel__title">
            Комфортний відпочинок
            <span>без компромісів</span>
          </h2>

          <p class="hotel__text">
            Після дня біля басейну або вечірки
            залишайтесь у комфортному номері.
            Сучасний інтер'єр, затишна атмосфера
            та все необхідне для приємного відпочинку.
          </p>

          <div class="hotel__features">
            <div class="feature">✓ Кондиціонер</div>
            <div class="feature">✓ Wi-Fi</div>
            <div class="feature">✓ Телевізор</div>
            <div class="feature">✓ Душова кімната</div>
            <div class="feature">✓ Комфортне ліжко</div>
            <div class="feature">✓ Паркінг</div>
          </div>

          <div class="hotel__bottom">

            <div class="price">
              <span>від</span>
              <strong>1500 ₴</strong>
              <small>за добу</small>
            </div>

            <a
              href="https://t.me/pink_pelikan_bot"
              target="_blank"
              rel="noopener"
              class="hotel__btn"
            >
              <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" style="flex-shrink:0"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.562 8.248-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.26 14.4l-2.95-.924c-.64-.204-.654-.64.136-.95l11.527-4.448c.533-.194 1 .131.59.17z"/></svg>
              Забронювати в Telegram
            </a>

          </div>

        </div>

        <!-- RIGHT -->
        <div class="hotel__image">
          <img
            src="@/assets/images/room.jpg"
            alt="Номер Pink Pelikan"
          >
          <div class="hotel__badge">Комфортний номер</div>
        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.hotel {
  scroll-margin-top: 100px;
  position: relative;
  padding: 140px 0;
  background: linear-gradient(to bottom, #09090c, #050505);
}

.hotel__grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 70px;
  align-items: center;
}

.hotel__label {
  display: inline-block;
  margin-bottom: 16px;
  color: var(--pink);
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: .85rem;
}

.hotel__title {
  margin: 0;
  color: white;
  font-size: clamp(2.2rem, 5vw, 4.5rem);
  line-height: 1.05;
}

.hotel__title span {
  display: block;
  color: var(--pink);
}

.hotel__text {
  margin-top: 30px;
  color: #a1a1aa;
  line-height: 1.9;
  font-size: 1.05rem;
  max-width: 600px;
}

.hotel__features {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 18px;
  margin-top: 40px;
}

.feature {
  padding: 18px 20px;
  color: white;
  border-radius: 18px;
  background: rgba(16,17,20,.8);
  border: 1px solid rgba(255,62,168,.08);
  font-size: .95rem;
}

.hotel__bottom {
  display: flex;
  align-items: center;
  gap: 30px;
  margin-top: 50px;
  flex-wrap: wrap;
}

.price {
  display: flex;
  flex-direction: column;
}

.price span { color: #a1a1aa; }
.price strong {
  color: var(--pink);
  font-size: 3rem;
  line-height: 1;
}
.price small { color: #a1a1aa; }

.hotel__btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 18px 32px;
  border-radius: 999px;
  text-decoration: none;
  color: white;
  font-weight: 700;
  font-size: 1rem;
  background: linear-gradient(135deg, #ff3ea8, #ff63c3);
  box-shadow: 0 0 30px rgba(255,62,168,.3);
  transition: .3s;
}

.hotel__btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 0 45px rgba(255,62,168,.5);
}

.hotel__image {
  position: relative;
  overflow: hidden;
  border-radius: 36px;
  height: 650px;
  border: 1px solid rgba(255,62,168,.15);
}

.hotel__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: .6s;
}

.hotel__image:hover img { transform: scale(1.06); }

.hotel__image::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(0,0,0,.7), transparent);
}

.hotel__badge {
  position: absolute;
  left: 24px;
  bottom: 24px;
  z-index: 2;
  padding: 14px 22px;
  color: white;
  border-radius: 999px;
  backdrop-filter: blur(20px);
  background: rgba(255,255,255,.08);
  border: 1px solid rgba(255,255,255,.1);
  font-size: .9rem;
}

@media (max-width: 1100px) {
  .hotel__grid { grid-template-columns: 1fr; }
  .hotel__image { height: 500px; }
}

@media (max-width: 768px) {
  .hotel { padding: 90px 0; }
  .hotel__features { grid-template-columns: 1fr; }
  .hotel__bottom {
    flex-direction: column;
    align-items: flex-start;
  }
  .hotel__btn { width: 100%; justify-content: center; }
  .hotel__image { height: 380px; border-radius: 24px; }
}
</style>
