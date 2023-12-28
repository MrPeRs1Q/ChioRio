<template>
  <Main/>
</template>

<script>
import Main from '@/views/Main.vue';

export default {
  name: 'App',
  components: {
    Main,
  }
}
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Gilroy', sans-serif;
  font-size: 24px;
}

html, body {
  height: 100vh;
  width: 100vw;
  overflow-x: hidden;
}

a {
  color: var(--black);
  text-decoration: none;
}

button {
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
}
</style>