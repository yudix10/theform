
<script setup>
import philosophyImage from '../assets/images/png/2-about-philosophy/картина-о-философии.png'
</script>

<template>
  <main class="about-page">
    <section class="about-hero">
      <div class="about-heading">
        <span class="eyebrow">ГАЛЕРЕЯ ПРЕДМЕТНОГО ДИЗАЙНА</span>
        <h1>О галерее <span>ФОРМА.</span></h1>
        <p>
          Пространство, в котором предметы становятся искусством,
          а каждая деталь обретает собственный голос.
        </p>
      </div>

      <img
        :src="philosophyImage"
        alt="Художественная композиция галереи ФОРМА"
      />
    </section>

    <section class="about-description">
      <span class="eyebrow">НАША ФИЛОСОФИЯ</span>
      <h2>Мы замечаем то, что остаётся.</h2>
      <p>
        «ФОРМА» — авторская цифровая галерея, посвящённая
        предметному дизайну. Мы исследуем взаимодействие формы,
        материала и эмоций, объединяя функциональность и искусство.
      </p>
    </section>
  </main>
</template>
