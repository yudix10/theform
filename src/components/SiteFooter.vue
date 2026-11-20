<script setup>
import logoUrl from '../assets/images/svg/forma-logo.svg'
import HomeUrl from '../assets/images/svg/Home.svg'
import FavoriteUrl from '../assets/images/svg/favourites.svg'
import HistoryUrl from '../assets/images/svg/history.svg'
import AboutUrl from '../assets/images/svg/about-us.svg'

const navigation = [
  { label: 'Главная', href: '#home' },
  { label: 'Коллекция', href: '#collection' },
  { label: 'Истории', href: '#stories' },
  { label: 'О галерее', href: '#about' },
]
</script>

<template>
  <footer class="site-footer">
    <div class="container footer-inner">
      <div class="footer-columns">
        <section class="footer-about">
          <a class="brand footer-brand" href="#home" aria-label="ФОРМА — главная">
            <img class="brand-logo-image" :src="logoUrl" alt="" />
            <span class="brand-name">ФОРМА</span>
          </a>
          <p class="footer-tagline">Искусство в каждой детали.</p>
          <p class="footer-description">Авторская цифровая галерея современного предметного дизайна. Пространство формы, материала и авторских идей.</p>
        </section>
        <nav class="footer-nav-block" aria-label="Навигация в подвале">
          <h2 class="footer-heading">Навигация</h2>
          <div class="footer-links">
            <a v-for="item in navigation" :key="item.href" :href="item.href">{{ item.label }}</a>
          </div>
        </nav>
        <section class="footer-contact-block">
          <h2 class="footer-heading">Контакты</h2>
          <div class="footer-contacts">
            <a href="mailto:hello@forma.gallery">hello@forma.gallery</a>
            <a href="tel:+79200017184">+7(920) 001-71-84</a>
          </div>
        </section>
      </div>
      <div class="footer-bottom">
        <small class="copyright">© ФОРМА · 2026. ВСЕ ПРАВА ЗАЩИЩЕНЫ.</small>
        <span class="credit">The product David Badalyan</span>
        <nav class="legal-links" aria-label="Правовая информация">
          <a href="#privacy">Политика конфиденциальности</a>
          <a href="#terms">Условия использования</a>
        </nav>
      </div>
    </div>
  </footer>
  <nav class="mobile-bottom-nav" aria-label="Мобильная навигация">
    <a href="#home" aria-label="Главная"><img class="icons-image" :src="HomeUrl" alt="" /><span>Главная</span></a>
    <a href="#collection" aria-label="Коллекция"><img class="icons-image" :src="FavoriteUrl" alt="" /><span>Коллекция</span></a>
    <a href="#stories" aria-label="Истории"><img class="icons-image" :src="HistoryUrl" alt="" /><span>Истории</span></a>
    <a href="#about" aria-label="О нас"><img class="icons-image" :src="AboutUrl" alt="" /><span>О нас</span></a>
  </nav>
</template>
