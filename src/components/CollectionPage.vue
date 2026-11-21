<script setup>
import { ref, computed } from 'vue';
import p01 from '../assets/images/png/1-products/01.png';
import p02 from '../assets/images/png/1-products/02.png';
import p03 from '../assets/images/png/1-products/03.png';
import p04 from '../assets/images/png/1-products/04.png';
import p05 from '../assets/images/png/1-products/05.png';
import p06 from '../assets/images/png/1-products/06.png';
import p07 from '../assets/images/png/1-products/07.png';
import p08 from '../assets/images/png/1-products/08.png';
import p09 from '../assets/images/png/1-products/09.png';
import p10 from '../assets/images/png/1-products/10.png';
import p11 from '../assets/images/png/1-products/11.png';
import p12 from '../assets/images/png/1-products/12.png';
const products = [
  {
    image: p01,
    category: 'МЕБЕЛЬ · 01',
    name: 'Кресло «Тишина»',
    description: 'Сочетание спокойной формы, мягкой текстуры и выразительной геометрии.',
    year: '2025',
    material: 'Дерево · кожа',
  },
  {
    image: p02,
    category: 'СВЕТ · 02',
    name: 'Светильник «Арка»',
    description: 'Свет становится самостоятельным объектом, формируя камерное настроение.',
    year: '2025',
    material: 'Металл · стекло',
  },
  {
    image: p03,
    category: 'КЕРАМИКА · 03',
    name: 'Объект «Терра»',
    description: 'Естественная пластика и тонкая фактура делают предмет выразительным.',
    year: '2026',
    material: 'Керамика',
  },
  {
    image: p04,
    category: 'АРТ-ОБЪЕКТЫ · 04',
    name: 'Композиция №04',
    description: 'Абстрактная композиция на границе предметного дизайна и искусства.',
    year: '2025',
    material: 'Смешанная техника',
  },
  {
    image: p05,
    category: 'МЕБЕЛЬ · 05',
    name: 'Стол «Баланс»',
    description: 'Сдержанная основа, ясная геометрия и натуральная древесина.',
    year: '2025',
    material: 'Орех · металл',
  },
  {
    image: p06,
    category: 'СВЕТ · 06',
    name: 'Лампа «Контур»',
    description: 'Светильник с мягким рассеянным светом для интерьерной композиции.',
    year: '2025',
    material: 'Металл · акрил',
  },
  {
    image: p07,
    category: 'АРТ-ОБЪЕКТЫ · 07',
    name: 'Чаша «Линия»',
    description: 'Скульптурная форма превращает утилитарный предмет в арт-объект.',
    year: '2026',
    material: 'Дерево',
  },
  {
    image: p08,
    category: 'МАТЕРИАЛЫ · 08',
    name: 'Фактура камня',
    description: 'Природный рисунок материала раскрывается через контраст и глубину.',
    year: '2025',
    material: 'Натуральный камень',
  },
  {
    image: p09,
    category: 'МЕБЕЛЬ · 09',
    name: 'Стул «Пауза»',
    description: 'Невесомый силуэт и мягкие пропорции для спокойного созерцания.',
    year: '2026',
    material: 'Текстиль · металл',
  },
  {
    image: p10,
    category: 'КЕРАМИКА · 10',
    name: 'Сосуд «Орбита»',
    description: 'Объекты с разной высотой и объёмом, объединённые общей фактурой.',
    year: '2025',
    material: 'Керамика',
  },
  {
    image: p11,
    category: 'АРХИТЕКТУРА · 11',
    name: 'Тихая архитектура',
    description: 'Эстетика пространства, света и фактуры.',
    year: '2026',
    material: 'Камень · свет',
  },
  {
    image: p12,
    category: 'ТЕКСТИЛЬ · 12',
    name: 'Световой объект',
    description: 'Фактуры и приглушённый свет создают цельное настроение.',
    year: '2025',
    material: 'Текстиль · дерево',
  },
];
const filters = ['ВСЕ ОБЪЕКТЫ', 'МЕБЕЛЬ', 'СВЕТ', 'КЕРАМИКА', 'АРТ-ОБЪЕКТЫ', 'МАТЕРИАЛЫ'];
const active = ref(filters[0]);
const selected = ref(null);
const visible = computed(() =>
  active.value === filters[0]
    ? products
    : products.filter((p) => p.category.startsWith(active.value)),
);
</script>
<template>
  <main class="collection-main">
    <section class="collection-intro">
      <div class="collection-title-row">
        <div>
          <span class="page-eyebrow">АРХИВ ПРЕДМЕТНОГО ДИЗАЙНА</span>
          <h1>Коллекция <em>форм.</em></h1>
        </div>
        <span class="collection-count">12 ОБЪЕКТОВ · 2026</span>
      </div>
      <p>Предметы, в которых форма, материал и функция становятся единым высказыванием.</p>
      <div class="collection-filters">
        <button v-for="f in filters" :key="f" :class="{ active: active === f }" @click="active = f">
          {{ f }}
        </button>
      </div>
    </section>
    <section class="collection-grid">
      <button v-for="p in visible" :key="p.category" class="product-card" @click="selected = p">
        <span class="product-image-wrap"><img :src="p.image" :alt="p.name" loading="lazy" /></span>
        <span class="product-card-meta">{{ p.category }}</span><span class="product-card-name">{{
          p.name
        }}</span
        ><span class="product-card-open">↗</span>
      </button>
    </section>
    <div v-if="selected" class="product-modal-backdrop" @click.self="selected = null">
      <article class="product-modal" role="dialog" aria-modal="true">
        <button class="modal-close" aria-label="Закрыть" @click="selected = null">×</button>
        <span class="page-eyebrow">{{ selected.category }}</span>
        <h2>{{ selected.name }}</h2>
        <img :src="selected.image" :alt="selected.name" />
        <p>{{ selected.description }}</p>
        <div class="modal-meta">
          <span><small>КОЛЛЕКЦИЯ</small>{{ selected.year }}</span
          ><span><small>МАТЕРИАЛ</small>{{ selected.material }}</span
          ><span><small>СТАТУС</small>В КОЛЛЕКЦИИ</span>
        </div>
      </article>
    </div>
  </main>
</template>
