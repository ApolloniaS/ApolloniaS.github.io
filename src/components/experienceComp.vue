<template>
  <div class="component-container" id="exp">
    <div class="experience">
      <div class="enum">02. Experience</div>
    </div>
    <div class="tools">
      <div class="tool-box">
        <div
          v-for="(icon, index) in icons"
          :key="icon"
          :class="'animate__animated animate__fadeInDown'"
          :style="{ 'animation-delay': `${(index + 1) * 0.5}s` }"
        >
          <i class="logos" :class="'devicon-' + icon"></i>
        </div>
      </div>
      <div class="experiences">
        <Carousel :items-to-show="2.5">
          <Slide v-for="exp in experiences" :key="exp.id">
            <div class="carousel__item">
              <div class="slide-card">
                {{ exp.role }} @ {{ exp.workplace }} ({{ exp.startdate }} - {{ exp.enddate }})
              </div>
            </div>
          </Slide>
          <template #addons>
            <Navigation />
            <Pagination />
          </template>
        </Carousel>
      </div>
    </div>
  </div>
  
</template>
  
<script setup lang="ts">
import 'animate.css'
import { Carousel, Slide, Navigation, Pagination } from 'vue3-carousel'
import { ref } from 'vue'

import 'vue3-carousel/dist/carousel.css'

const icons = [
  'csharp-plain',
  'vuejs-plain',
  'angularjs-plain',
  'html5-plain',
  'css3-plain',
  'javascript-plain',
  'typescript-plain',
  'nuxtjs-plain',
  'sass-original',
  'materialui-plain',
  'bootstrap-plain',
]

const experiences = ref([
  {
    id: 1,
    role: "Web Developer & Innovator",
    workplace: "Mind Technology",
    startdate: "11/2022",
    enddate: "now",
  },
  {
    id: 2,
    role: "IT Developer",
    workplace: "DECIS",
    startdate: "05/2021",
    enddate: "10/2022",
  },
  {
    id: 3,
    role: "Trainee",
    workplace: "Interface3",
    startdate: "06/2020",
    enddate: "05/2021",
  },
])
</script>
  
<style scoped>
@import url('https://cdn.jsdelivr.net/gh/devicons/devicon@v2.15.1/devicon.min.css');
.tool-box {
  width: 80%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;

  > div {
    margin: 1rem;
  }
}

.logos {
  font-size: 48px;
  color: #aa7da1;
}

.experiences {
  width: 80%;
  margin: auto;
}

.carousel__item {
  min-height: 200px;
  width: 100%;
  background-color: var(--vc-clr-primary);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid white;
}

.slide-card {
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
  text-align: center;
  border-radius: 5px;
  width: 150px;
  height: 150px; 
}
</style>
  