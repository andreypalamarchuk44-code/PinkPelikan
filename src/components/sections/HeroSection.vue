<script setup>

import heroVideo from '@/assets/video/pool.mp4'

</script>


<template>
  <section class="hero" id="top">

    <!-- Background Video (pool) -->
    <div class="hero__bg">
    <video
  autoplay
  muted
  loop
  playsinline
  class="hero__video"
>
  <source :src="heroVideo" type="video/mp4">
</video>
      <!-- fallback image -->
      <img
        src="@/assets/images/pool.jpg"
        alt="Pink Pelikan Pool"
        class="hero__fallback"
      >
    </div>

    <!-- Overlay -->
    <div class="hero__overlay"></div>

    <!-- Glow -->
    <div class="hero__glow"></div>

    <div class="container hero__content">

      <span class="hero__eyebrow">
        Літній комплекс відпочинку та розваг
      </span>

      <h1 class="hero__title">
        PINK PELIKAN —
        <span>
          МІСЦЕ, ДЕ ЛІТО
          ТРИВАЄ ДОВШЕ
        </span>
      </h1>

      <p class="hero__text">
        Басейн, готель, кухня та незабутні вечірки
        на одній території у Ладижині.
        Відпочивай, смакуй, танцюй.
      </p>

      <div class="hero__actions">

        <a
          href="https://t.me/pink_pelikan_bot"
          target="_blank"
          rel="noopener"
          class="btn btn--primary"
        >
          <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" style="flex-shrink:0"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.562 8.248-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.26 14.4l-2.95-.924c-.64-.204-.654-.64.136-.95l11.527-4.448c.533-.194 1 .131.59.17z"/></svg>
          Забронювати номер
        </a>

        <a
          href="#restaurant"
          class="btn btn--secondary"
        >
          Меню бару
        </a>

      </div>

    </div>

    <a href="#features" class="hero__scroll" aria-label="Прокрутити вниз">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12l7 7 7-7"/></svg>
    </a>

  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero__bg {
  position: absolute;
  inset: 0;
}

.hero__video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.hero__fallback {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}

.hero__overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    90deg,
    rgba(0,0,0,.88) 0%,
    rgba(0,0,0,.55) 55%,
    rgba(0,0,0,.65) 100%
  );
}

.hero__glow {
  position: absolute;
  width: 700px;
  height: 700px;
  top: -200px;
  right: -100px;
  border-radius: 50%;
  background: radial-gradient(
    circle,
    rgba(255,62,168,.28),
    transparent 70%
  );
  filter: blur(50px);
  pointer-events: none;
}

.hero__content {
  position: relative;
  z-index: 3;
  max-width: 760px;
  padding-top: 100px;
  padding-bottom: 60px;
}

.hero__eyebrow {
  display: inline-block;
  margin-bottom: 18px;
  color: var(--pink);
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: .9rem;
}

.hero__title {
  margin: 0;
  font-size: clamp(2.6rem, 7vw, 6rem);
  line-height: .95;
  font-weight: 800;
  color: white;
}

.hero__title span {
  display: block;
  margin-top: 10px;
  color: var(--pink);
}

.hero__text {
  margin-top: 28px;
  max-width: 620px;
  color: #d1d5db;
  font-size: 1.1rem;
  line-height: 1.8;
}

.hero__actions {
  display: flex;
  gap: 16px;
  margin-top: 40px;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 16px 30px;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  transition: .3s;
  white-space: nowrap;
}

.btn--primary {
  color: white;
  background: linear-gradient(135deg, #ff3ea8, #ff62c2);
  box-shadow: 0 0 35px rgba(255,62,168,.35);
}

.btn--primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 0 50px rgba(255,62,168,.5);
}

.btn--secondary {
  color: white;
  border: 1px solid rgba(255,255,255,.2);
  background: rgba(255,255,255,.07);
  backdrop-filter: blur(20px);
}

.btn--secondary:hover {
  border-color: var(--pink);
  background: rgba(255,62,168,.1);
}

.hero__scroll {
  position: absolute;
  left: 50%;
  bottom: 30px;
  transform: translateX(-50%);
  z-index: 3;
  color: rgba(255,255,255,.6);
  text-decoration: none;
  animation: bounce 2s infinite;
  transition: color .3s;
}

.hero__scroll:hover {
  color: var(--pink);
}

@keyframes bounce {
  0%,100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(10px); }
}

@media (max-width: 768px) {
  .hero__content {
    padding-top: 130px;
  }

  .hero__actions {
    flex-direction: column;
  }

  .btn {
    text-align: center;
    justify-content: center;
    width: 100%;
    max-width: 320px;
    padding: 16px 24px;
  }

  .hero__title {
    font-size: clamp(2rem, 10vw, 3rem);
  }

  .hero__glow {
    width: 400px;
    height: 400px;
  }
}

@media (max-width: 480px) {
  .hero__title {
    font-size: 2rem;
  }

  .hero__text {
    font-size: 1rem;
  }
}
</style>
