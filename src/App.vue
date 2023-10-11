<script setup lang="ts">
import AboutMeComp from './components/aboutMeComp.vue'
import LandingComp from './components/landingComp.vue'
import ExperienceComp from './components/experienceComp.vue'
import Test from './components/test.vue'

// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <LandingComp></LandingComp>
  <AboutMeComp></AboutMeComp>
  <Test></Test>
  <ExperienceComp></ExperienceComp>

  <div class="nav f-28">
    <p><a href="#top">00</a></p>
    <p><a href="#about">01</a></p>
    <p><a href="#exp">02</a></p>
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
