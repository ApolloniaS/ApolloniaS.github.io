<template>
  <LandingComp></LandingComp>
  <AboutMeComp></AboutMeComp>
  <!-- <Test></Test> -->
  <ExperienceComp></ExperienceComp>
  <div class="component-container">test</div>
  
  <div class="nav f-28">
    <p>
      <a class="nav-item" href="#top">
        00
      </a>
    </p>
    <p>
      <a class="nav-item" href="#about">
        01
      </a>
    </p>
    <p>
      <a class="nav-item" href="#exp">
        02
      </a>
    </p>
  </div>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
    
    <div class="wrapper">
      <HelloWorld msg="You did it!" />
      
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>
  
  <RouterView /> -->
</template>

<script setup lang="ts">
import AboutMeComp from './components/aboutMeComp.vue'
import LandingComp from './components/landingComp.vue'
import ExperienceComp from './components/experienceComp.vue'
import Test from './components/test.vue'
import { onMounted, onBeforeUnmount } from 'vue'

const handleScroll = () => {
  const navItems = document.querySelectorAll('.nav-item')
  let activeSectionId: string | null = null

  document.querySelectorAll('.component-container').forEach((section: HTMLElement) => {
    const rect = section.getBoundingClientRect()
    if (rect.top <= 0 && rect.bottom >= 0) {
      activeSectionId = section.id
    }
  })
  navItems.forEach((item: HTMLElement) => item.classList.remove('active'))
  
  if (activeSectionId) {
    console.log(activeSectionId)
    const correspondingNavItem = document.querySelector(`a.nav-item[href="#${activeSectionId}"]`)
    console.log(correspondingNavItem)
    if (correspondingNavItem) {
      correspondingNavItem.classList.add('active')
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.nav {
  position: fixed;
  right: 1rem;
  top: 50%;
  transform: translate(0, -50%);
  font-family: "DoublePixel", sans-serif;
  color: #1f081c;
  border-right: 1px solid #1f081c;
  
  > p {
    padding-right: 1rem;
  }
}

a.active {
  font-weight: bold;
  color: red; 
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
