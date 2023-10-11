<template>
  <div class="component-container" id="top">
    <div class="intro f-28">
      <Typed :options="options">
        <p class="typing"></p>   
      </Typed>
      <Typed v-if="showSecond" :options="options2">
        <p class="typing"></p>
      </Typed>
      <Typed v-if="showThird" :options="options3">
        <p class="typing"></p>
      </Typed>
      <Transition>
        <div 
        class="CTA" 
        v-if="isTypedFinished" 
        @mouseover="hover = true" 
        @mouseleave="hover = false"
        >
          <a href="#about">
            <p>
              About me <font-awesome-icon :icon="['fas', hover ? 'chevron-down' : 'chevron-right']"></font-awesome-icon>
            </p>
          </a>
          </div>
      </Transition>
    </div> 
  </div>
</template>

<script setup lang="ts">
import { Typed } from "@duskmoon/vue3-typed-js"
import type { TypedOptions } from "@duskmoon/vue3-typed-js"
import { ref } from "vue"

const showSecond = ref(false)
const showThird = ref(false)
const isTypedFinished = ref(false)

const hover = ref(false)

const options: TypedOptions = {
  strings: ["...^300 Hello! ^500 I'm Apollonia (●'◡'●)"],
  typeSpeed: 30,
  showCursor: false,
  onComplete: () => {
    showSecond.value = true
  }
}
const options2: TypedOptions = {
  strings: ['...^300 Belgian web developer'],
  typeSpeed: 30,
  showCursor: false,
  onComplete: () => {
    showThird.value = true
  }
}

const options3: TypedOptions = {
  strings: ['...^300 Front-end and fullstack projects'],
  typeSpeed: 30,
  showCursor: false,
  onComplete: () => {
    isTypedFinished.value = true
  }
}
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 2s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
.intro {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-family: "FreePixel", sans-serif;
    color: #8d98b4;
}

a {
    z-index: 1;
    color: #aa7da1 !important;
    text-transform: uppercase;
}
</style>