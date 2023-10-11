<template>
    <div class="component-container" id="top">
        <div class="intro">
            <Typed :options="options">
                <p class="typing">
                </p>   
            </Typed>
            <Typed v-if="showSecond" :options="options2">
                <p class="typing">
                </p>
            </Typed>
            <Typed v-if="showThird" :options="options3">
                <p class="typing">
                </p>
            </Typed>
            <p><a href="#about">
                About me <font-awesome-icon icon="fa-solid fa-chevron-right" />
            </a></p>
        </div> 
    </div>
</template>

<script setup lang="ts">
import { Typed } from "@duskmoon/vue3-typed-js";
import type { TypedOptions } from "@duskmoon/vue3-typed-js";
import { ref } from "vue"

const showSecond = ref(false);
const showThird = ref(false);

const options: TypedOptions = {
  strings: ["...^300 Hello! ^500 I'm Apollonia."],
  typeSpeed: 30,
  showCursor: false,
  onComplete: () => {
    showSecond.value = true;
  }
}
const options2: TypedOptions = {
  strings: ['...^300 Belgian web developer'],
  typeSpeed: 30,
  showCursor: false,
  onComplete: () => {
    showThird.value = true;
  }
};

const options3: TypedOptions = {
  strings: ['...^300 Front-end and fullstack projects'],
  typeSpeed: 30,
  showCursor: false
};
</script>

<style scoped>
.intro {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-family: "FreePixel", sans-serif;
    color: #8d98b4;
}

a {
    color: #aa7da1 ;
    text-transform: uppercase;
}
</style>