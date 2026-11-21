<script setup>
import featuredImage from '../assets/images/png/5-stories-of-objects/Image.png'
import interiorImage from '../assets/images/png/5-stories-of-objects/Image-1.png'
import lightImage from '../assets/images/png/5-stories-of-objects/Image-2.png'
import materialImage from '../assets/images/png/5-stories-of-objects/Image-3.png'
import arrowIcon from '../assets/images/svg/Arrow 1.2.svg';

const stories = [
  {
    image: interiorImage,
    category: 'ПРОСТРАНСТВО · 4 МИНУТЫ',
    title: 'Тишина в интерьере: искусство паузы',
    date: '12.10.2026',
    href: '#story-interior',
    alt: 'Спокойный интерьер с мягкой мебелью и деревянными деталями',
  },
  {
    image: lightImage,
    category: 'СВЕТ · 5 МИНУТ',
    title: 'Свет, который создаёт атмосферу',
    date: '28.09.2026',
    href: '#story-light',
    alt: 'Светильник над обеденным столом',
  },
  {
    image: materialImage,
    category: 'МАТЕРИАЛЫ · 3 МИНУТЫ',
    title: 'Несовершенство как эстетика',
    date: '04.09.2026',
    href: '#story-materials',
    alt: 'Фактура натурального камня в интерьере',
  },
]
</script>

<template>
  <main class="stories-main" id="stories">
    <div class="stories-container">
      <header class="stories-intro">
        <span class="stories-kicker">ЖУРНАЛ ГАЛЕРЕИ</span>
        <h1>Истории<br />предметов.</h1>
        <p>Разговоры о материалах, деталях и людях, которые формируют визуальную культуру.</p>
      </header>

      <article class="stories-feature">
        <img
          class="stories-feature-image"
          :src="featuredImage"
          alt="Крупный план деревянного предмета мебели"
        />
        <div class="stories-feature-meta">МАТЕРИАЛЫ · 6 МИНУТ ЧТЕНИЯ</div>
        <h2>Тактильность как новый<br class="stories-desktop-break" /> язык дизайна.</h2>
        <p>Почему мы всё чаще выбираем вещи, которые хочется не только видеть, но и ощущать.</p>
        <a class="stories-read-link" href="#story-tactility">ЧИТАТЬ ИСТОРИЮ</a>
      </article>

      <div class="stories-list">
        <article
          v-for="story in stories"
          :key="story.href"
          class="stories-list-item"
        >
          <a class="stories-list-image" :href="story.href" :aria-label="story.title">
            <img :src="story.image" :alt="story.alt" />
          </a>
          <div class="stories-list-copy">
            <span class="stories-list-meta">{{ story.category }}</span>
            <h3><a :href="story.href">{{ story.title }}</a></h3>
            <time>{{ story.date }}</time>
          </div>
          <a class="stories-list-arrow" :href="story.href" :aria-label="`Открыть: ${story.title}`">
          <span>
            <img :src="arrowIcon" alt="history">
          </span>
          </a>
        </article>
      </div>
    </div>
  </main>
</template>
