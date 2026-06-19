<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import Navbar from './components/layout/Navbar.vue'
import HeroSection from './components/sections/HeroSection.vue'
import FeaturesSection from './components/sections/FeaturesSection.vue'
import HotelSection from './components/sections/HotelSection.vue'
import PoolSection from './components/sections/PoolSection.vue'
import RestaurantSection from './components/sections/RestaurantSection.vue'
import EventsSection from './components/sections/EventsSection.vue'
import GallerySection from './components/sections/GallerySection.vue'
import ReviewsSection from './components/sections/ReviewsSection.vue'
import ContactSection from './components/sections/ContactSection.vue'
import Footer from './components/layout/Footer.vue'

const showFloat = ref(false)

const handleScroll = () => {
  showFloat.value = window.scrollY > 400
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<template>
  <Navbar />

  <main>
    <HeroSection />
    <FeaturesSection />
    <HotelSection />
    <PoolSection />
    <RestaurantSection />
    <EventsSection />
    <GallerySection />
    <ReviewsSection />
    <ContactSection />
  </main>

  <Footer />

  <!-- Sticky Telegram Button -->
  <transition name="float">
    <a
      v-if="showFloat"
      href="https://t.me/pink_pelikan_bot"
      target="_blank"
      rel="noopener"
      class="float-tg"
      aria-label="Написати в Telegram"
    >
      <svg width="26" height="26" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.562 8.248-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.26 14.4l-2.95-.924c-.64-.204-.654-.64.136-.95l11.527-4.448c.533-.194 1 .131.59.17z"/>
      </svg>
      <span class="float-tg__label">Бронювати</span>
    </a>
  </transition>
</template>

<style>
.float-tg {
  position: fixed;
  bottom: 28px;
  right: 28px;
  z-index: 999;

  display: flex;
  align-items: center;
  gap: 10px;

  padding: 14px 22px;

  border-radius: 999px;

  background: linear-gradient(135deg, #ff3ea8, #ff63c3);
  color: white;
  text-decoration: none;
  font-weight: 600;
  font-size: .95rem;

  box-shadow:
    0 4px 24px rgba(255,62,168,.45),
    0 0 0 0 rgba(255,62,168,.4);

  animation: pulse-ring 2.5s infinite;

  transition: transform .3s;
}

.float-tg:hover {
  transform: translateY(-3px);
}

@keyframes pulse-ring {
  0% { box-shadow: 0 4px 24px rgba(255,62,168,.45), 0 0 0 0 rgba(255,62,168,.4); }
  60% { box-shadow: 0 4px 24px rgba(255,62,168,.45), 0 0 0 12px rgba(255,62,168,0); }
  100% { box-shadow: 0 4px 24px rgba(255,62,168,.45), 0 0 0 0 rgba(255,62,168,0); }
}

.float-enter-active,
.float-leave-active { transition: .4s; }
.float-enter-from,
.float-leave-to {
  opacity: 0;
  transform: translateY(20px);
}

@media (max-width: 480px) {
  .float-tg {
    bottom: 18px;
    right: 16px;
    padding: 12px 16px;
  }

  .float-tg__label {
    display: none;
  }
}
</style>
