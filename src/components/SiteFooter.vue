<script setup>
import logoUrl from '../assets/images/forma-logo.svg'
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
    <a href="#home" aria-label="Главная"><svg viewBox="0 0 24 24"><path d="M3 10.5 12 3l9 7.5v10H14v-6h-4v6H3z"/></svg><span>Главная</span></a>
    <a href="#collection" aria-label="Коллекция"><svg viewBox="0 0 24 24"><path d="M20.8 8.8c0 5.1-8.8 11-8.8 11s-8.8-5.9-8.8-11A4.8 4.8 0 0 1 12 6.1a4.8 4.8 0 0 1 8.8 2.7Z"/></svg><span>Коллекция</span></a>
    <a href="#stories" aria-label="Истории"><svg viewBox="0 0 24 24"><path d="M3.5 11a8.5 8.5 0 1 1 1.8 5.2"/><path d="M3.5 4.5V11h6.3M12 7v5l3.2 2"/></svg><span>Истории</span></a>
    <a href="#about" aria-label="О нас"><svg viewBox="0 0 24 24"><circle cx="8" cy="5" r="3"/><path d="M2.5 20v-2.2A5.3 5.3 0 0 1 7.8 12h.4a5.3 5.3 0 0 1 5.3 5.3V20M17 4h4M19 2v4M16 11h5M16 15h5M16 19h5"/></svg><span>О нас</span></a>
  </nav>
</template>
