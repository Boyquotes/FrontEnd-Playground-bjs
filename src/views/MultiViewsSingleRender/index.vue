<template>
  <section class="wrapper">

    <div id="mountedDOM"></div>

    <div class="gui-container" ref="GUIcontainer"></div>

    <div class="caption">
      <p>Two cubes within two scenes rendered by single renderer.</p>
      <p>The key of renderer is that `renderer.setScissor` overlapping two scenes in view.</p>
    </div>
  </section>
</template>
<script lang="js">
import { run, dispose } from "./main";
export default {
  mounted() {
    run(document.getElementById("mountedDOM"));
  },
  beforeDestroy() {
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

.mask {
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: row;
  width: 100%;
  height: 100%;
}

.part {
  flex: 1;
}

.caption {
  position: absolute;
  color: white;
  bottom: 15px;
  left: 50%;
  transform: translate(-50%);
  text-align: center;
}
</style>