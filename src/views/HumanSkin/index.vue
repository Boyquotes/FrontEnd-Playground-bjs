<template>
  <section class="wrapper">
    <div id="mountedDOM" ref="mountedDOM"></div>
    <div class="stat-container"></div>
    <div class="gui-container" ref="GUIcontainer"></div>
    <div class="introductions">
      <p class="keywords">
        Fast subsurface scattering in Physical
      </p>
      <p class="exteral-link">
        Reference: 
        <a target="_blank" href="https://github.com/lo-th/three.lab">
          lo-th / three.lab
        </a>
      </p>
    </div>
  </section>
</template>
<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { run, dispose } from "./main";

const mountedDOM = ref()
onMounted(() => {
  run(mountedDOM.value)
})
onBeforeUnmount(() => {
  dispose()
})
</script>
<style scoped>
.wrapper,
#mountedDOM {
  width: 100%;
  height: 100%;
}

.stat-container {
  position: absolute;
  top: 0;
  left: 15px;
}

.gui-container {
  position: absolute;
  top: 0;
  left: 80px;
}

.introductions {
  position: absolute;
  left: 50%;
  bottom: 1em;
  transform: translateX(-50%);
  color: white;
  text-align: center;
}
.introductions .keywords,
.introductions .exteral-link,
.introductions a {
  font-family: "Consolas";
}
</style>
