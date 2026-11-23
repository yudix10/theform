<script setup>
import { ref, computed } from 'vue';
import plusIcon from '../assets/images/svg/+.svg';
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
    category: '01 / МЕБЕЛЬ',
    name: 'Кресло «Тишина»',
    description: 'Сочетание спокойной формы, мягкой текстуры и выразительной геометрии.',
    year: '2025',
    material: 'Дерево · кожа',
  },
  {
    image: p02,
    category: '02 / СВЕТ',
    name: 'Светильник «Арка»',
    description: 'Свет становится самостоятельным объектом, формируя камерное настроение.',
    year: '2025',
    material: 'Металл · стекло',
  },
  {
    image: p03,
    category: '03 / КЕРАМИКА',
    name: 'Объект «Терра»',
    description: 'Естественная пластика и тонкая фактура делают предмет выразительным.',
    year: '2026',
    material: 'Керамика',
  },
  {
    image: p04,
    category: '04 / АРТ-ОБЪЕКТЫ',
    name: 'Композиция №04',
    description: 'Абстрактная композиция на границе предметного дизайна и искусства.',
    year: '2025',
    material: 'Смешанная техника',
  },
  {
    image: p05,
    category: '05 / МЕБЕЛЬ',
    name: 'Стол «Баланс»',
    description: 'Сдержанная основа, ясная геометрия и натуральная древесина.',
    year: '2025',
    material: 'Орех · металл',
  },
  {
    image: p06,
    category: '06 / СВЕТ',
    name: 'Лампа «Контур»',
    description: 'Светильник с мягким рассеянным светом для интерьерной композиции.',
    year: '2025',
    material: 'Металл · акрил',
  },
  {
    image: p07,
    category: '07 / КЕРАМИКА',
    name: 'Чаша «Линия»',
    description: 'Скульптурная форма превращает утилитарный предмет в арт-объект.',
    year: '2026',
    material: 'Дерево',
  },
  {
    image: p08,
    category: '08 / АРТ-ОБЪЕКТЫ',
    name: 'Форма пространства',
    description: 'Природный рисунок материала раскрывается через контраст и глубину.',
    year: '2025',
    material: 'Натуральный камень',
  },
  {
    image: p09,
    category: '09 / МЕБЕЛЬ',
    name: 'Стул «Пауза»',
    description: 'Невесомый силуэт и мягкие пропорции для спокойного созерцания.',
    year: '2026',
    material: 'Текстиль · металл',
  },
  {
    image: p10,
    category: '10 / КЕРАМИКА',
    name: 'Сосуд «Орбита»',
    description: 'Объекты с разной высотой и объёмом, объединённые общей фактурой.',
    year: '2025',
    material: 'Керамика',
  },
  {
    image: p11,
    category: '11 / АРТ-ОБЪЕКТЫ',
    name: 'Тихая архитектура',
    description: 'Эстетика пространства, света и фактуры.',
    year: '2026',
    material: 'Камень · свет',
  },
  {
    image: p12,
    category: '12 / СВЕТ',
    name: 'Световой объект',
    description: 'Фактуры и приглушённый свет создают цельное настроение.',
    year: '2025',
    material: 'Текстиль · дерево',
  },
];
const filters = ['ВСЁ 12', 'МЕБЕЛЬ 03', 'СВЕТ 03', 'КЕРАМИКА 03', 'АРТ-ОБЪЕКТЫ 03'];

const active = ref(filters[0]);
const selected = ref(null);

const visible = computed(() => {
  if (active.value === 'ВСЁ 12') {
    return products;
  }

  const categoryName = active.value.replace(/\s+\d+$/, '');

  return products.filter((product) => product.category.includes(categoryName));
});
</script>
<template>
  <main class="collection-main">
    <section class="collection-intro">
      <div class="collection-title-row">
        <div>
          <span class="page-eyebrow">АРХИВ ОБЪЕКТОВ 2026</span>
          <h1>Коллекция <em>форм.</em></h1>
        </div>
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
        }}</span>
        <span class="product-card-open" aria-hidden="true"></span>
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
          ><span><small>ЦЕНА</small>{{ selected.price }}</span>
        </div>
      </article>
    </div>
  </main>
</template>
