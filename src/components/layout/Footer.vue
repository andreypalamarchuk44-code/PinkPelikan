<template>
  <footer class="footer">

    <div class="footer__glow"></div>

    <div class="container">

      <div class="footer__center">

        <img
          src="/logo.png"
          alt="Pink Pelikan"
          class="footer__logo"
        >

        <h2>
          Твоє літо починається
          <span>тут</span>
        </h2>

        <p>
          Басейн · Готель · Бар · Кухня · Кальяни · Вечірки
        </p>

        <a
          href="tel:+380974587955"
          class="footer__phone"
        >
          +38 (097) 458 79 55
        </a>

        <div class="footer__socials">

          <a
            href="https://www.instagram.com/pink_pelican_2024/"
            target="_blank"
          >
            Instagram
          </a>

          <a
            href="#"
            target="_blank"
          >
            Facebook
          </a>

        </div>

      </div>

      <div class="footer__bottom">

        <span>
          © 2026 Pink Pelikan
        </span>

        <span>
          м. Ладижин · вул. Хлібозаводська 1-А
        </span>

      </div>

    </div>

  </footer>
</template>

<style scoped>
.footer{
  position:relative;
  overflow:hidden;

  padding:100px 0 40px;

  background:#050505;

  border-top:
    1px solid rgba(255,62,168,.08);
}

.footer__glow{
  position:absolute;

  width:600px;
  height:600px;

  top:-300px;
  left:50%;

  transform:translateX(-50%);

  border-radius:50%;

  background:
    radial-gradient(
      circle,
      rgba(255,62,168,.15),
      transparent 70%
    );

  pointer-events:none;
}

.footer__center{
  text-align:center;
}

.footer__logo{
  height:90px;
  margin-bottom:30px;
}

.footer h2{
  margin:0;

  color:white;

  font-size:
    clamp(2.5rem,5vw,4rem);
}

.footer h2 span{
  color:var(--pink);
}

.footer p{
  margin:20px 0;

  color:#9ca3af;
}

.footer__phone{
  display:inline-block;

  margin-top:10px;

  color:white;

  font-size:1.5rem;
  font-weight:700;

  text-decoration:none;
}

.footer__socials{
  margin-top:35px;

  display:flex;
  justify-content:center;
  gap:20px;
}

.footer__socials a{
  padding:14px 22px;

  border-radius:999px;

  text-decoration:none;

  color:white;

  background:
    rgba(255,255,255,.06);

  border:
    1px solid rgba(255,62,168,.15);

  transition:.3s;
}

.footer__socials a:hover{
  background:var(--pink);
}

.footer__bottom{
  margin-top:60px;

  padding-top:25px;

  border-top:
    1px solid rgba(255,255,255,.05);

  display:flex;
  justify-content:space-between;

  color:#6b7280;
}

@media(max-width:768px){

  .footer__bottom{
    flex-direction:column;
    gap:12px;
    text-align:center;
  }

  .footer__socials{
    flex-direction:column;
    align-items:center;
  }
}
</style>