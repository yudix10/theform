<script setup>
import SiteHeader from './components/SiteHeader.vue'
import SiteFooter from './components/SiteFooter.vue'

import heroImage from './assets/images/png/Home.png'
import philosophyImage from './assets/images/png/2-about-philosophy/картина-о-философии.png'
import logoImage from './assets/images/svg/forma1.svg'
import FocusSection from './components/FocusSection.vue'
</script>

<template>
  <SiteHeader />

  <main class="home-main">

    <!-- ПЕРВЫЙ ЭКРАН -->
    <section class="hero" id="home">
      <img class="hero-image" :src="heroImage" alt="Интерьер современной галереи" />

      <div class="hero-overlay"></div>

      <div class="hero-content">
        <h1>
          Искусство<br />
          в каждой<br />
          <span>детали.</span>
        </h1>

        <p class="hero-description">
          Исследуем предметный дизайн через форму, материал и<br class="desktop-break" />
          эмоцию. Галерея объектов, которые говорят без слов.
        </p>

        <a href="#collection" class="hero-button">
          <span>Исследовать коллекцию</span>
          <span class="hero-arrow">⟶</span>
        </a>
      </div>

      <div class="hero-bottom">
        <span>ПРОСТРАНСТВО СОВРЕМЕННОГО ДИЗАЙНА</span>
        <a href="#philosophy">ЛИСТАЙТЕ ВНИЗ ↓</a>
      </div>
    </section>
    <div class="mobile-section-label">ОБЪЕКТЫ · 2026</div>

    <!-- БЛОК О ФИЛОСОФИИ -->
    <section class="philosophy" id="philosophy">

      <div class="philosophy-image-wrap">
        <span class="section-number">01 — О ФИЛОСОФИИ</span>
        <img
          class="philosophy-image"
          :src="philosophyImage"
          alt="Абстрактная художественная композиция"
        />
      </div>

      <div class="philosophy-content">
        <span class="eyebrow">МЕНЬШЕ, НО ЗНАЧИМЕЕ</span>

        <h2>
          Мы замечаем то, что
          <span>остаётся.</span>
        </h2>

        <p>
          «ФОРМА» — авторская цифровая галерея, посвящённая предметам
          с характером. Мы собираем объекты, в которых функциональность
          встречается с искусством, а простота становится выразительным языком.
        </p>

        <a href="#about" class="philosophy-link">
          БОЛЬШЕ О ГАЛЕРЕЕ
        </a>
      </div>

      <div class="philosophy-symbol">
        <img :src="logoImage" alt="Знак галереи ФОРМА" />
      </div>

    </section>

    <FocusSection />

  </main>

  <SiteFooter />
</template>