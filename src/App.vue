<template>
  <a-scene>
    <a-box
        color="#0095DD"
        position="0 1 0"
        rotation="20 40 0">
    </a-box>
    <a-camera
        look-controls
        position="0 1 4"
        cursor-visible="true"
        cursor-scale="2"
        cursor-color="#0095DD"
        cursor-opacity="0.5">
    </a-camera>
    <a-sky color="#DDDDDD"></a-sky>
  </a-scene>
</template>

<script>

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
