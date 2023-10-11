<template>
  <div class="component-container" id="about">
    <div class="about-me">
      <div class="enum">
        01. About me
      </div>
      <div class="who-am-i f-28">
        <p>
          Web developer living in Brussels and interested in a wide range of projects.
        </p>
        <p>
          > Former translator with a huge interest in everything related to languages
        </p>
        <p>
          > Lover of both video games and board games
        </p>
        <p>
          > Avid reader who's yet to learn how to put a good book down
        </p>
        <div class="CTA" @mouseover="hover = true" @mouseleave="hover = false">
          <p>
            <a href="#exp">
              Technical skills and <br/>IT experience <font-awesome-icon :icon="['fas', hover ? 'chevron-down' : 'chevron-right']"></font-awesome-icon>
            </a>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const hover = ref(false)

</script>

<style scoped>
.who-am-i {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-family: "FreePixel", sans-serif;
  color: #8d98b4;
}

a {
  text-transform: uppercase;
  color: #aa7da1;
}
</style>