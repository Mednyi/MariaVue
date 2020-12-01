<template lang="pug">
  #app
    Header
    router-view
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: 'IBM Plex Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #161616;
  font-size: 16px;
  display: grid;
  grid: 'h' max-content
        'm' auto;
  height: 100vh;
}
</style>
