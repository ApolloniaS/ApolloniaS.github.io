<template>
    <div class="container">
      <div class="panel blue">Panel Blue</div>
      <div class="panel red">Panel Red</div>
      <div class="panel gray">Panel Gray</div>
      <div class="panel blue">Panel More</div>

    </div>
  </template>
  
  <script setup lang="ts">
  import { onMounted } from "vue"
  import gsap from "gsap"
  import ScrollTrigger from "gsap/ScrollTrigger"
  
  onMounted(() => {
    gsap.registerPlugin(ScrollTrigger)
  
    const panels = document.querySelectorAll(".panel")
  
    const scrollTween = gsap.to(panels, {
      xPercent: -100 * (panels.length - 1),
      ease: "none",
      scrollTrigger: {
        trigger: ".container",
        // pin: true,
        scrub: 0.1,
        end: "+=3000",
      },
    })
  
    panels.forEach((panel, index) => {
      gsap.to(panel, {
        scrollTrigger: {
          trigger: panel,
          start: "top center",
          toggleActions: "play none none reset",
        },
      })
    })
  })
  </script>
  
  <style scoped>
  .container {
    width: 100vw; 
    height: 50vh;
    display: flex;
    flex-wrap: nowrap;
    overflow: hidden;
  }
  
  .panel {
    width: 50vw;
    height: 50vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 24px;
    font-weight: bold;
    flex-shrink: 0;
  }
  
  .blue {
    background-color: blue;
    color: #fff;
  }
  
  .red {
    background-color: red;
    color: #fff;
  }
  
  .gray {
    background-color: grey;
    color: #fff;
  }
  </style>
  