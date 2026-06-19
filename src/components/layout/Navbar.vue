<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import {
  IconBrandInstagram,
  IconBrandFacebook,
  IconMenu2,
  IconX
} from '@tabler/icons-vue'

const mobileMenu = ref(false)
const scrolled = ref(false)

const handleScroll = () => {
  scrolled.value = window.scrollY > 30
}

const closeMenu = () => {
  mobileMenu.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header
    class="navbar"
    :class="{ 'navbar--scrolled': scrolled }"
  >
    <div class="container navbar__inner">

      <!-- LOGO -->
      <a href="#top" class="navbar__logo" @click="closeMenu">
        <img
          src="/logo.png"
          alt="Pink Pelikan"
        />
      </a>

      <!-- DESKTOP MENU -->
      <nav class="navbar__menu">
        <a href="#features">Переваги</a>
        <a href="#hotel">Готель</a>
        <a href="#pool">Басейн</a>
        <a href="#restaurant">Кухня & Бар</a>
        <a href="#events">Події</a>
        <a href="#gallery">Афіша</a>
        <a href="#contacts">Контакти</a>
      </nav>

      <!-- RIGHT -->
      <div class="navbar__actions">

        <a
          href="https://www.instagram.com/pink_pelican_2024/"
          target="_blank"
          class="social"
          aria-label="Instagram"
        >
          <IconBrandInstagram :size="22" />
        </a>

        <a
          href="https://facebook.com"
          target="_blank"
          class="social"
          aria-label="Facebook"
        >
          <IconBrandFacebook :size="22" />
        </a>

        <a
          href="https://t.me/pink_pelikan_bot"
          target="_blank"
          rel="noopener"
          class="book-btn"
        >
          Бронювати
        </a>

        <button
          class="burger"
          @click="mobileMenu = !mobileMenu"
          :aria-label="mobileMenu ? 'Закрити меню' : 'Відкрити меню'"
        >
          <IconMenu2 v-if="!mobileMenu" :size="26" />
          <IconX v-else :size="26" />
        </button>
      </div>
    </div>

    <!-- MOBILE MENU -->
    <transition name="menu">
      <div
        v-if="mobileMenu"
        class="mobile-menu"
      >
        <a href="#features" @click="closeMenu">Переваги</a>
        <a href="#hotel" @click="closeMenu">Готель</a>
        <a href="#pool" @click="closeMenu">Басейн</a>
        <a href="#restaurant" @click="closeMenu">Кухня & Бар</a>
        <a href="#events" @click="closeMenu">Події</a>
        <a href="#gallery" @click="closeMenu">Aфіша</a>
        <a href="#contacts" @click="closeMenu">Контакти</a>
        <a
          href="https://t.me/pink_pelikan_bot"
          target="_blank"
          rel="noopener"
          class="mobile-book-btn"
          @click="closeMenu"
        >
          📲 Забронювати в Telegram
        </a>
      </div>
    </transition>
  </header>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 16px;
  left: 0;
  width: 100%;
  z-index: 1000;
  transition: .35s ease;
  padding: 0 16px;
  box-sizing: border-box;
}

.navbar__inner {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 80px;
  border-radius: 24px;
  background: rgba(8, 8, 10, 0.25);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255,255,255,.05);
  box-sizing: border-box;
}

.navbar--scrolled .navbar__inner {
  background: rgba(10,10,12,.92);
  border-color: rgba(255,62,168,.15);
  box-shadow: 0 0 35px rgba(255,62,168,.12);
}

.navbar__logo img {
  height: 56px;
  object-fit: contain;
  display: block;
}

.navbar__menu {
  display: flex;
  gap: 28px;
  flex-wrap: nowrap;
}

.navbar__menu a {
  color: white;
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
  transition: .3s;
  white-space: nowrap;
}

.navbar__menu a:hover { color: #ff3ea8; }

.navbar__actions {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-shrink: 0;
}

.social {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  border: 1px solid rgba(255,255,255,.08);
  transition: .3s;
  text-decoration: none;
  flex-shrink: 0;
}

.social:hover {
  background: #ff3ea8;
  border-color: #ff3ea8;
}

.book-btn {
  padding: 12px 22px;
  border-radius: 999px;
  text-decoration: none;
  color: white;
  font-weight: 600;
  font-size: .9rem;
  background: linear-gradient(135deg, #ff3ea8, #ff5cb9);
  box-shadow: 0 0 25px rgba(255,62,168,.4);
  transition: .3s;
  white-space: nowrap;
  flex-shrink: 0;
}

.book-btn:hover { transform: translateY(-2px); }

.burger {
  display: none;
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  padding: 4px;
  flex-shrink: 0;
}

.mobile-menu {
  display: none;
}

@media (max-width: 1100px) {
  .navbar__menu { gap: 18px; }
  .navbar__menu a { font-size: 13px; }
}

@media (max-width: 1024px) {
  .navbar__menu { display: none; }
  .burger { display: block; }

  .mobile-menu {
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin: 10px 16px 0;
    padding: 20px;
    border-radius: 20px;
    background: #0e0f13;
    border: 1px solid rgba(255,62,168,.15);
    backdrop-filter: blur(20px);
  }

  .mobile-menu a {
    color: white;
    text-decoration: none;
    padding: 12px 16px;
    border-radius: 12px;
    transition: .2s;
    font-size: 1rem;
  }

  .mobile-menu a:hover {
    background: rgba(255,62,168,.1);
    color: var(--pink);
  }

  .mobile-book-btn {
    margin-top: 10px;
    background: linear-gradient(135deg, #ff3ea8, #ff63c3) !important;
    text-align: center;
    font-weight: 600 !important;
    border-radius: 999px !important;
  }
}

@media (max-width: 768px) {
  .book-btn { display: none; }
  .social { display: none; }
  .navbar__logo img { height: 44px; }
  .navbar { top: 10px; padding: 0 10px; }
  .navbar__inner { height: 68px; padding: 0 16px; border-radius: 18px; }
}

.menu-enter-active,
.menu-leave-active { transition: .3s; }
.menu-enter-from,
.menu-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
