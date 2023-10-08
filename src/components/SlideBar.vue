<script setup>
import { ref, computed } from 'vue';

function getImageUrl(path, name) {
  return new URL(`../assets/${path}/${name}`, import.meta.url).href;
}

const sliders = [
  {
    title: 'Brand naming & guidelines',
    img: 'image-slide-1.jpg',
    infos: ['Lean Product Roadmap', '2019 Project'],
  },
  {
    title: 'Brand identity & merchandise',
    img: 'image-slide-2.jpg',
    infos: ['New Majestic Hotel', '2018 Project'],
  },
  {
    title: 'Brand identity & web design',
    img: 'image-slide-3.jpg',
    infos: ['Crypto Dashboard', '2016 Project'],
  },
];

let idx = ref(0);
let animationKey = ref(0);

const content = computed(() => {
  return sliders[idx.value];
});

const prevSlide = () => {
  idx.value = (idx.value - 1 + sliders.length) % sliders.length;
  animationKey.value++;
};

const nextSlide = () => {
  idx.value = (idx.value + 1) % sliders.length;
  animationKey.value++;
};
</script>

<template>
  <section class="slider">
    <div class="slider-container flex">
      <div class="slider-txt">
        <h3 class="animate" :key="animationKey">
          {{ content.title }}
          <img src="../assets/desktop/bg-pattern-wavy-white.svg" alt="" />
        </h3>
        <div class="btns flex-align">
          <button @click="prevSlide()" class="btn-circle"><img src="../assets/desktop/icon-arrow-previous.svg" alt="" /></button>
          <button @click="nextSlide()" class="btn-circle"><img src="../assets/desktop/icon-arrow-next.svg" alt="" /></button>
        </div>
      </div>
      <div class="slider-img">
        <picture>
          <source media="(min-width: 1024px)" :srcset="getImageUrl('desktop', content.img)" />
          <source media="(min-width: 768px)" :srcset="getImageUrl('tablet', content.img)" />
          <img :src="getImageUrl('mobile', content.img)" alt="#" class="animate" :key="animationKey" />
        </picture>
        <div class="infos animate" :key="animationKey">
          <p class="info-p">
            {{ content.infos[0] }}
          </p>
          <p class="span">{{ content.infos[1] }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.animate-enter-active,
.animate-leave-active {
  transition: transform 1.5s;
}
.animate-enter,
.animate-leave-to {
  transform: translateX(100%);
}
.slider-container {
  justify-content: space-between;
  margin-bottom: 3rem;
  isolation: isolate;
  position: relative;
  height: 45.5rem;
}
.slider-txt {
  background-color: var(--clr-bg-black);
  display: grid;
  place-content: center;
  width: calc(100% - var(--card-width));
  height: 33rem;
  position: relative;
  z-index: 2;
}

.animate {
  animation: move-left 1.5s forwards;
}

h3 {
  font-size: var(--size-2);
  line-height: 64px;
  max-width: 27.813rem;
  position: relative;
  margin-bottom: 3rem;
  color: var(--clr-white);
}

h3 img {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: -12.5rem;
  z-index: 1;
}

.btns {
  gap: 1rem;
}

.slider-img {
  position: absolute;
  right: 0;
  left: 30%;
  top: 0;
  bottom: 0;
}

.slider-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.infos {
  position: absolute;
  right: 3rem;
  bottom: 3rem;
}

.info-p {
  font-size: 20px;
  font-weight: bold;
  color: var(--clr-white);
}

.span {
  font-size: 18px;
  color: var(--clr-white);
  margin-top: 0.5rem;
}
</style>
