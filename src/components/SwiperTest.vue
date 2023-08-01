<script setup lang="ts">
// import function to register Swiper custom elements
import { register } from 'swiper/element/bundle';
import { ref } from 'vue';
// register Swiper custom elements
register();


const sidebar = ref(false);



const reviewData = [
  {
    desc: 'I\'ve never used a theme as versatile and flexible as Vuexy. It\'s my go to for building dashboard sites on almost any project.',
    rating: 5,
    name: 'Eugenia Moore',
    position: 'Founder of Hubspot',
  },
  {
    desc: 'Materio is awesome, and I particularly enjoy knowing that if I get stuck on something.',
    rating: 5,
    name: 'Tommy haffman',
    position: 'Founder of Levis',
  },
  {
    desc: 'This template is superior in so many ways. The code, the design, the regular updates, the support.. It’s the whole package. Excellent Work.',
    rating: 4,
    name: 'Eugenia Moore',
    position: 'CTO of Airbnb',
  },
  {
    desc: 'All the requirements for developers have been taken into consideration, so I’m able to build any interface I want.',
    rating: 5,
    name: 'Sara Smith',
    position: 'Founder of Continental',
  },
  {
    desc: 'Materio is awesome, and I particularly enjoy knowing that if I get stuck on something.',
    rating: 5,
    name: 'Tommy haffman',
    position: 'Founder of Levis',
  },
  {
    desc: 'I\'ve never used a theme as versatile and flexible as Vuexy. It\'s my go to for building dashboard sites on almost any project.',
    rating: 5,
    name: 'Eugenia Moore',
    position: 'Founder of Hubspot',
  },
  {
    desc: 'Materio is awesome, and I particularly enjoy knowing that if I get stuck on something.',
    rating: 5,
    name: 'Tommy haffman',
    position: 'Founder of Levis',
  },
  {
    desc: 'This template is superior in so many ways. The code, the design, the regular updates, the support.. It’s the whole package. Excellent Work.',
    rating: 4,
    name: 'Eugenia Moore',
    position: 'CTO of Airbnb',
  },
  {
    desc: 'All the requirements for developers have been taken into consideration, so I’m able to build any interface I want.',
    rating: 5,
    name: 'Sara Smith',
    position: 'Founder of Continental',
  },
  {
    desc: 'Materio is awesome, and I particularly enjoy knowing that if I get stuck on something.',
    rating: 5,
    name: 'Tommy haffman',
    position: 'Founder of Levis',
  },
]
</script>

<template>
  <h1>Swiper Test</h1>

  <VNavigationDrawer v-model="sidebar" disable-resize-watcher touchless :touch="false">
    <div>This is navigation drawer</div>
  </VNavigationDrawer>

  <VBtn @click="sidebar = !sidebar">Open Drawer</VBtn>
  <swiper-container slides-per-view="1" space-between="5" centered-slides="true" loop="true" autoplay-delay="3000"
    autoplay-disable-on-interaction="false" :pagination="{
      clickable: 'true',
    }" :injectStyles="[
  `
          .swiper-pagination{
            position: static;
            margin-block: 1rem;
          },
          .swiper-pagination-bullet-active{
            width: 1rem;
          }

      `]" :breakpoints="{
        1200: {
          slidesPerView: 4,
          spaceBetween: 20,
        },
        992: {
          slidesPerView: 3,
          spaceBetween: 20,
        },
        768: {
          slidesPerView: 2,
          spaceBetween: 20,
        },
      }">
    <swiper-slide v-for="(data, index) in reviewData" :key="index">
      <VCard flat border class="h-100 d-flex align-stretch">
        <VCardText class="pa-6 d-flex flex-column justify-space-between align-center">

          <div class="text-body-1 text-high-emphasis text-center">
            {{ data.desc }}
          </div>
          <VRating :model-value="data.rating" color="warning" readonly />
          <div class="text-center">
            <span class="text-body-1 text-high-emphasis font-weight-medium">
              {{ data.name }}
            </span>
            <br>
            <span class="text-body-2">{{ data.position }}</span>
          </div>
        </VCardText>
      </VCard>
    </swiper-slide>
  </swiper-container>
</template>
