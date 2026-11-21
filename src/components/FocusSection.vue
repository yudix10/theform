<script setup>
import furnitureImage from '../assets/images/png/3-in-focus/in-focus1.png'
import lightImage from '../assets/images/png/3-in-focus/in-focus2.png'
import ceramicImage from '../assets/images/png/3-in-focus/in-focus3.png'
</script>

<template>
  <section class="focus-section" id="collection">
    <div class="focus-inner">
      <div class="focus-heading">
        <div>
          <span class="focus-eyebrow">
          ОТОБРАННОЕ ВРУЧНУЮ
          </span>

          <h2>
          В центре <em>внимания.</em>
          </h2>

        </div>

        <a href="#collection" class="focus-all">
        <span>ВСЯ КОЛЛЕКЦИЯ</span>
        </a>
      </div>

      <div class="focus-gallery">
        <article class="focus-card focus-card--furniture">
          <div class="focus-image">
            <img :src="furnitureImage" alt="Авторское кресло" />
          </div>
          <div class="focus-caption">
            <span>МЕБЕЛЬ</span>
            <span>КРЕСЛО «ТИШИНА»</span>
          </div>
        </article>

        <article class="focus-card focus-card--light">
          <div class="focus-image">
            <img :src="lightImage" alt="Дизайнерский светильник" />
          </div>
          <div class="focus-caption">
            <span>СВЕТ</span>
            <span>СВЕТИЛЬНИК «АРКА»</span>
          </div>
        </article>

        <article class="focus-card focus-card--ceramic">
          <div class="focus-image">
            <img :src="ceramicImage" alt="Керамическая ваза" />
          </div>
          <div class="focus-caption">
            <span>КЕРАМИКА</span>
            <span>ОБЪЕКТ «ТЕРРА»</span>
          </div>
        </article>
      </div>
    </div>
  </section>

  <section class="approach-section">
    <div class="approach-content">
      <span class="approach-eyebrow">НАШ ПОДХОД</span>

      <blockquote>
        «Хороший предмет<br />
        не требует внимания.<br />
        <em>Он его удерживает.</em>»
      </blockquote>

      <span class="approach-caption">ФИЛОСОФИЯ ГАЛЕРЕИ «ФОРМА»</span>
    </div>
  </section>
</template>