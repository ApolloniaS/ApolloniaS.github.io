<template>
    <div class="component-container" id="exp">
      <div class="experience">
        <div class="enum">02. Experience</div>
      </div>
      <div class="exp-wrapper">
        <div class="scroll-wrapper" ref="scrollWrapper">
          <div class="most-recent" ref="mostRecent">
            <p class="test">Mind Technology</p>
            <p class="test">Decision Engineering</p>
            <p class="test">Interface3</p>
            <p class="test">More ?</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  import { gsap } from 'gsap'
  import { ref, onMounted } from 'vue'
  
  const scrollWrapper = ref<HTMLElement | null>(null);
  const mostRecent = ref<HTMLElement | null>(null);
  
  onMounted(() => {
    if (scrollWrapper.value && mostRecent.value) {
      scrollWrapper.value.addEventListener('scroll', () => {
        const scrollX = scrollWrapper.value.scrollLeft;
  
        gsap.to(mostRecent.value, {
          x: -scrollX,
          duration: 0.5,
          ease: 'power2.inOut',
        });
      });
    }
  });
  </script>
  
  <style scoped>
  .test {
    width: 50vw;
    height: 50vh;
    background-color: green;
  }
  .exp-wrapper {
    width: 100%;
    overflow: hidden;
  }
  
  .scroll-wrapper {
    width: 100%;
    overflow-x: auto; /* Use "auto" for horizontal scrolling */
    white-space: nowrap;
    -webkit-overflow-scrolling: touch;
  }
  
  .most-recent {
    display: inline-block;
    white-space: nowrap;
    padding: 20px;
    /* Add this to ensure the <p> elements display horizontally */
    flex-direction: row;
  }
  
  .most-recent p {
    /* Add this to ensure the <p> elements display horizontally */
    display: inline-block;
    margin: 0 10px; /* Optional: Add margin between <p> elements */
  }
  </style>
  