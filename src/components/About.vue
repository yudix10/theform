<script setup>
import { ref } from 'vue';
import aboutImage from '../assets/images/png/4-about-the-gallery/Image.png';

import logoMark from '../assets/images/svg/forma1.svg';
const name = ref(''),
  email = ref(''),
  message = ref(''),
  sent = ref(false);
function submitForm() {
  if (!name.value.trim() || !email.value.trim() || !message.value.trim()) return;
  const subject = encodeURIComponent('Сообщение для галереи ФОРМА');
  const body = encodeURIComponent(`Имя: ${name.value}\nE-mail: ${email.value}\n\n${message.value}`);
  window.location.href = `mailto:hello@forma.gallery?subject=${subject}&body=${body}`;
  sent.value = true;
}
</script>
<template>
  <main class="about-main">
    <section class="about-intro">
      <span class="page-eyebrow"> О ГАЛЕРЕЕ · 2026 </span>
      <h1>Форма — это<br /><em>больше,</em><br />чем объект.</h1>
      <p>
        Мы создаём пространство для внимательного взгляда на предметный дизайн. Здесь каждая линия,
        фактура и пропорция имеют значение.
      </p>
      <img class="about-hero-image" :src="aboutImage" alt="Светильник в интерьере галереи" />
    </section>
    <section class="about-philosophy">
      <div class="about-philosophy-copy">
        <span class="page-eyebrow">НАША ФИЛОСОФИЯ</span>
        <h2>Замечать важное.<br />Чувствовать настоящее.</h2>
        <p>
          «ФОРМА» — независимая цифровая галерея предметного дизайна. Мы исследуем объекты на
          пересечении искусства, ремесла и повседневной жизни.
        </p>
      </div>
      <div class="about-manifesto">
        <p>Замечать важное.</p>
        <img :src="logoMark" alt="" /><em>Чувствовать настоящее.</em
        ><span>Мы интересуемся не только внешней формой, но и тем, что остаётся с человеком.</span>
      </div>
    </section>
    <section class="about-principles">
      <span class="page-eyebrow">ПРИНЦИПЫ ГАЛЕРЕИ</span>
      <div class="principle-grid">
        <article>
          <span>01</span>
          <h3>Материал</h3>
          <p>Честность фактуры и уважение к природе материала.</p>
        </article>
        <article>
          <span>02</span>
          <h3>Форма</h3>
          <p>Баланс пропорций, выразительности и ясности.</p>
        </article>
        <article>
          <span>03</span>
          <h3>Смысл</h3>
          <p>Каждый объект несёт идею, которая остаётся с человеком.</p>
        </article>
      </div>
    </section>
    <section class="about-contact">
      <div class="about-contact-heading">
        <span class="page-eyebrow">БУДЕМ НА СВЯЗИ</span>
        <h2>Есть идея?<em>Обсудим.</em></h2>
        <p>Открыты к сотрудничеству, предложениям и новым историям о предметном дизайне.</p>
        <a href="mailto:hello@forma.gallery">hello@forma.gallery</a
        ><a href="tel:+79200017184">+7(920) 001-71-84</a>
      </div>
      <form class="contact-form" @submit.prevent="submitForm">
        <label>ВАШЕ ИМЯ<input v-model="name" required placeholder="Как к вам обращаться" /></label
        ><label
          >E-MAIL<input
            v-model="email"
            type="email"
            required
            placeholder="name@example.com" /></label
        ><label
          >СООБЩЕНИЕ<textarea
            v-model="message"
            required
            rows="3"
            placeholder="Расскажите о вашей идее"
          ></textarea></label
        ><button type="submit">ОТПРАВИТЬ СООБЩЕНИЕ <span>⟶</span></button
        ><small v-if="sent">Почтовое приложение подготовит ваше сообщение.</small
        ><small v-else>Нажимая «Отправить», вы соглашаетесь на обработку данных.</small>
      </form>
    </section>
  </main>
</template>
