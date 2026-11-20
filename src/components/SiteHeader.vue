<script setup>
import logoUrl from '../assets/images/svg/forma-logo.svg'
</script>

<template>
  <div class="topline">
    <span>НЕЗАВИСИМАЯ ГАЛЕРЕЯ ПРЕДМЕТНОГО ДИЗАЙНА</span>
    <span class="topline-location">Нижний Новгород · 2026</span>
  </div>
  <header class="site-header">
    <div class="header-main">
      <a class="brand" href="#home" aria-label="ФОРМА — главная">
        <img class="brand-logo-image" :src="logoUrl" alt="" />
        <span class="brand-name">ФОРМА</span>
      </a>
      <nav class="header-nav" aria-label="Основная навигация">
        <a href="#home">Главная</a><a href="#collection">Коллекция</a>
        <a href="#stories">Истории</a><a href="#about">О галерее</a>
      </nav>
      <a class="header-contact" href="mailto:hello@forma.gallery">Связаться с нами</a>
      <div class="mobile-category">Объекты · 2026</div>
    </div>
  </header>
</template>
