<template>
  <section class="wrapper">
    <div id="mountedDOM"></div>
    <div class="gui-container" ref="GUIcontainer"></div>
    <div class="caption">
      <p>'GroundProjectedSkybox' has been commited in ThreeJs R151.</p>
      <a href="https://threejs.org/examples/?q=env#webgl_materials_envmaps_groundprojected" target="_blank">https://threejs.org/examples/?q=env#webgl_materials_envmaps_groundprojected</a>
    </div>
  </section>
</template>
<script lang="js">
import { run,dispose } from "./main";
export default {
  mounted() {
    run(document.getElementById("mountedDOM"));
  },
  beforeDestroy(){
    dispose()
  }
};
</script>
<style scoped>
.wrapper,
#mountedDOM {
  width: 100%;
  height: 100%;
}
.gui-container {
  position: absolute;
  top: 0;
  left: 15px;
}
.caption{
  position: absolute;
  bottom: 15px;
  left: 50%;
  transform: translate(-50%);
  text-align: center;
}
</style>
