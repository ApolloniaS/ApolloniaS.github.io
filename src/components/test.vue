<template>
    <div class="container">
      <div class="panel blue">
      <div class="panel-content">
        <div class="company-name">COMPANY NAME</div>
        <div class="role">ROLE</div>
        <div class="dates">
          <span class="start-date">Start Date: MM/DD/YYYY</span>
          <span class="end-date">End Date: MM/DD/YYYY</span>
        </div>
        <div class="tasks">Tasks</div>
      </div>
    </div>
    <div class="panel red">
      <div class="panel-content">
        <div class="company-name">COMPANY NAME</div>
        <div class="role">ROLE</div>
        <div class="tasks">Tasks</div>
      </div>
    </div>
    <div class="panel grey">
      <div class="panel-content">
        <div class="company-name">COMPANY NAME</div>
        <div class="role">ROLE</div>
        <div class="tasks">Tasks</div>
      </div>
    </div>
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
    width: 30vw;
    height: 50vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 24px;
    font-weight: bold;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 2rem;
    margin: 1rem;
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
  