<script setup>
import {
  IconBrandInstagram,
  IconBrandFacebook,
  IconPhone,
  IconMapPin,
  IconBrandTelegram
} from '@tabler/icons-vue'
</script>

<template>
  <section
    id="contacts"
    class="contacts"
  >
    <div class="container">

      <div class="contacts__box">

        <span class="contacts__label">
          Контакти
        </span>

        <h2>
          Чекаємо на вас у
          <span>Pink Pelikan</span>
        </h2>

        <p>
          Забронюйте номер або столик вже сьогодні.
        </p>

        <div class="contact-item">
          <IconPhone :size="22"/>
          <a href="tel:+380974587955">+38 (097) 458 79 55</a>
        </div>

        <div class="contact-item">
          <IconMapPin :size="22"/>
          <span>м. Ладижин, вул. Хлібозаводська 1-А</span>
        </div>

        <!-- TELEGRAM BOOKING -->
        <a
          href="https://t.me/pink_pelikan_bot"
          target="_blank"
          rel="noopener"
          class="tg-book-btn"
        >
          <IconBrandTelegram :size="22" />
          Забронювати через Telegram
        </a>

        <div class="socials">
          <a href="https://www.instagram.com/pink_pelican_2024/" target="_blank" aria-label="Instagram">
            <IconBrandInstagram :size="26"/>
          </a>
          <a href="https://t.me/pink_pelikan_bot" target="_blank" aria-label="Telegram">
            <IconBrandTelegram :size="26"/>
          </a>
          <a href="#" aria-label="Facebook">
            <IconBrandFacebook :size="26"/>
          </a>
        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.contacts {
  scroll-margin-top: 100px;
  padding: 140px 0;
  background: #050505;
}

.contacts__box {
  max-width: 860px;
  margin: auto;
  text-align: center;
  padding: 70px;
  border-radius: 40px;
  background: #101114;
  border: 1px solid rgba(255,62,168,.12);

  p {
    color: #ffff;
  }
}

.contacts__label {
  color: var(--pink);
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: .85rem;
}

.contacts h2 {
  margin: 20px 0;
  color: white;
  font-size: clamp(2rem, 5vw, 4rem);
  line-height: 1.15;
}

.contacts h2 span { color: var(--pink); }

.contacts > .contacts__box > p {
  color: #9ca3af;
  line-height: 1.8;
}

.contact-item {
  margin-top: 22px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  color: white;
  font-size: 1.05rem;
}

.contact-item a {
  color: white;
  text-decoration: none;
  transition: color .3s;
}

.contact-item a:hover { color: var(--pink); }

.tg-book-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  margin-top: 40px;
  padding: 18px 36px;
  border-radius: 999px;
  text-decoration: none;
  color: white;
  font-weight: 700;
  font-size: 1rem;
  background: linear-gradient(135deg, #ff3ea8, #ff63c3);
  box-shadow: 0 0 30px rgba(255,62,168,.35);
  transition: .3s;
}

.tg-book-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 0 50px rgba(255,62,168,.5);
}

.socials {
  margin-top: 40px;
  display: flex;
  justify-content: center;
  gap: 16px;
}

.socials a {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  background: #18191d;
  border: 1px solid rgba(255,62,168,.15);
  transition: .3s;
  text-decoration: none;
}

.socials a:hover {
  background: var(--pink);
  border-color: var(--pink);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .contacts { padding: 80px 0; }
  .contacts__box {
    padding: 40px 24px;
    border-radius: 28px;
  }
}

@media (max-width: 480px) {
  .contacts__box { padding: 32px 18px; }
  .tg-book-btn { width: 100%; justify-content: center; padding: 16px 24px; }
}
</style>
