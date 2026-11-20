<script setup>
import { ref, computed, onMounted, onBeforeUnmount, watch } from 'vue'
import SiteHeader from './components/SiteHeader.vue'
import SiteFooter from './components/SiteFooter.vue'
import FocusSection from './components/FocusSection.vue'
import StoriesPage from './components/StoriesPage.vue'
import CollectionPage from './components/CollectionPage.vue'
import AboutPage from './components/AboutPage.vue'
import heroImage from './assets/images/png/Home.png'
import philosophyImage from './assets/images/png/2-about-philosophy/картина-о-философии.png'
import logoImage from './assets/images/svg/forma1.svg'

const hash=ref(window.location.hash||'#home')
const page=computed(()=>hash.value==='#collection'?'collection':(hash.value==='#stories'||hash.value.startsWith('#story-'))?'stories':hash.value==='#about'?'about':'home')
function sync(){hash.value=window.location.hash||'#home';window.scrollTo(0,0)}
onMounted(()=>window.addEventListener('hashchange',sync))
onBeforeUnmount(()=>window.removeEventListener('hashchange',sync))
watch(page, p=>{document.title=({home:'ФОРМА — галерея предметного дизайна',collection:'Коллекция — ФОРМА',stories:'Истории предметов — ФОРМА',about:'О галерее — ФОРМА'})[p]})
</script>
<template>
 <SiteHeader :page="page"/>
 <main v-if="page==='home'" class="home-main">
  <section class="hero" id="home"><img class="hero-image" :src="heroImage" alt="Интерьер современной галереи"><div class="hero-overlay"></div><div class="hero-content"><h1>Искусство<br>в каждой<br><span>детали.</span></h1><p class="hero-description">Исследуем предметный дизайн через форму, материал и<br class="desktop-break"> эмоцию. Галерея объектов, которые говорят без слов.</p><a href="#collection" class="hero-button"><span>Исследовать коллекцию</span><span class="hero-arrow">⟶</span></a></div><div class="hero-bottom"><span>ПРОСТРАНСТВО СОВРЕМЕННОГО ДИЗАЙНА</span><a href="#philosophy">ЛИСТАЙТЕ ВНИЗ ↓</a></div></section>
  <div class="mobile-section-label">ОБЪЕКТЫ · 2026</div>
  <section class="philosophy" id="philosophy"><div class="philosophy-image-wrap"><span class="section-number">01 — О ФИЛОСОФИИ</span><img class="philosophy-image" :src="philosophyImage" alt="Абстрактная художественная композиция"></div><div class="philosophy-content"><span class="eyebrow">МЕНЬШЕ, НО ЗНАЧИМЕЕ</span><h2>Мы замечаем то, что <span>остаётся.</span></h2><p>«ФОРМА» — авторская цифровая галерея, посвящённая предметам с характером. Мы собираем объекты, в которых функциональность встречается с искусством, а простота становится выразительным языком.</p><a href="#about" class="philosophy-link">БОЛЬШЕ О ГАЛЕРЕЕ</a></div><div class="philosophy-symbol"><img :src="logoImage" alt="Знак галереи ФОРМА"></div></section>
  <FocusSection/>
 </main>
 <CollectionPage v-else-if="page==='collection'"/>
 <StoriesPage v-else-if="page==='stories'"/>
 <AboutPage v-else/>
 <SiteFooter/>
</template>
