<script setup>
</script>

<template>
  <section
    id="pool"
    class="pool"
  >
    <div class="container">

      <div class="pool__grid">

        <!-- PHOTO -->

        <div class="pool__image">

          <img
            src="@/assets/images/pool.jpg"
            alt="Басейн Pink Pelikan"
          >

          <div class="pool__floating">
            Літній сезон 2026
          </div>

        </div>

        <!-- CONTENT -->

        <div class="pool__content">

          <span class="pool__label">
            Басейн
          </span>

          <h2 class="pool__title">
            Відпочинок,
            який починається
            <span>біля води</span>
          </h2>

          <p class="pool__text">
            Просторий басейн, комфортна зона
            відпочинку, шезлонги та атмосфера,
            яка змушує повертатися знову.
          </p>

          <!-- PRICE CARD -->

          <div class="pool__price-card">

            <div class="price-main">

              <span>
                Вхід
              </span>

              <strong>
                0 ₴
              </strong>

            </div>

            <p>
              Користування басейном
              для гостей комплексу
            </p>

          </div>

          <!-- SERVICES -->

          <div class="pool__services">

            <div class="service-card">

              <h3>
                350 ₴
              </h3>

              <p>
                Шезлонг +
                парасоля +
                рушник
              </p>

            </div>

            <div class="service-card">

              <h3>
                50 ₴
              </h3>

              <p>
                Додатковий рушник
              </p>

            </div>

          </div>

          <a
            href="https://t.me/pink_pelikan_bot"
            target="_blank"
            rel="noopener"
            class="pool__btn"
          >
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor" style="flex-shrink:0"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.562 8.248-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.26 14.4l-2.95-.924c-.64-.204-.654-.64.136-.95l11.527-4.448c.533-.194 1 .131.59.17z"/></svg>
            Забронювати в Telegram
          </a>

        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.pool {
  scroll-margin-top: 100px;
  position: relative;

  padding: 140px 0;

  background:
    linear-gradient(
      to bottom,
      #050505,
      #09090d
    );
}

.pool__grid {
  display: grid;

  grid-template-columns:
    1.1fr .9fr;

  gap: 80px;

  align-items: center;
}

.pool__image {
  position: relative;

  overflow: hidden;

  border-radius: 36px;

  height: 720px;

  border:
    1px solid rgba(255,62,168,.15);
}

.pool__image img {
  width: 100%;
  height: 100%;

  object-fit: cover;

  transition: .8s;
}

.pool__image:hover img {
  transform: scale(1.05);
}

.pool__image::after {
  content: '';

  position: absolute;
  inset: 0;

  background:
    linear-gradient(
      to top,
      rgba(0,0,0,.75),
      transparent
    );
}

.pool__floating {
  position: absolute;

  left: 25px;
  bottom: 25px;

  z-index: 3;

  padding: 16px 24px;

  border-radius: 999px;

  color: white;

  background:
    rgba(255,255,255,.08);

  backdrop-filter: blur(18px);

  border:
    1px solid rgba(255,255,255,.08);
}

.pool__label {
  display: inline-block;

  margin-bottom: 15px;

  color: var(--pink);

  letter-spacing: 2px;
  text-transform: uppercase;
  font-size: .85rem;
}

.pool__title {
  margin: 0;

  color: white;

  font-size:
    clamp(2.8rem,5vw,4.8rem);

  line-height: 1.05;
}

.pool__title span {
  display: block;

  color: var(--pink);
}

.pool__text {
  margin-top: 28px;

  color: #a1a1aa;

  line-height: 1.9;

  max-width: 520px;
}

.pool__price-card {
  margin-top: 40px;

  padding: 32px;

  border-radius: 28px;

  background:
    rgba(16,17,20,.85);

  border:
    1px solid rgba(255,62,168,.15);

  box-shadow:
    0 0 35px rgba(255,62,168,.08);
}

.price-main {
  display: flex;

  align-items: center;
  justify-content: space-between;
}

.price-main span {
  color: #cfcfcf;
}

.price-main strong {
  color: var(--pink);

  font-size: 4rem;
  line-height: 1;
}

.pool__price-card p {
  margin: 15px 0 0;

  color: #9ca3af;
}

.pool__services {
  display: grid;

  grid-template-columns:
    repeat(2,1fr);

  gap: 20px;

  margin-top: 25px;
}

.service-card {
  padding: 24px;

  border-radius: 24px;

  background:
    rgba(16,17,20,.8);

  border:
    1px solid rgba(255,62,168,.08);
}

.service-card h3 {
  margin: 0 0 10px;

  color: white;

  font-size: 2rem;
}

.service-card p {
  margin: 0;

  color: #9ca3af;

  line-height: 1.6;
}

.pool__btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;

  margin-top: 35px;

  padding: 18px 34px;

  border-radius: 999px;

  text-decoration: none;

  color: white;

  font-weight: 700;

  background:
    linear-gradient(
      135deg,
      #ff3ea8,
      #ff69c6
    );

  box-shadow:
    0 0 35px rgba(255,62,168,.3);

  transition: .3s;
}

.pool__btn:hover {
  transform: translateY(-3px);
}

@media (max-width: 1100px) {

  .pool__grid {
    grid-template-columns: 1fr;
  }

  .pool__image {
    height: 520px;
  }
}

@media (max-width: 768px) {

  .pool {
    padding: 90px 0;
  }

  .pool__services {
    grid-template-columns: 1fr;
  }

  .pool__image {
    height: 380px;
  }

  .price-main strong {
    font-size: 3rem;
  }
}

@media (max-width: 480px) {
  .pool__image {
    height: 260px;
    border-radius: 20px;
  }
  .pool__price-card {
    padding: 24px 18px;
  }
}
</style>