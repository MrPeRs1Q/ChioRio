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

  &::-webkit-scrollbar-button {
    background-repeat: no-repeat;
    width: 10px;
    height: 0;
  }

  &::-webkit-scrollbar-thumb {
    -webkit-border-radius: 0;
    border-radius: 10px;
    background-color: var(--black);
  }

  &::-webkit-scrollbar-thumb:hover {
    opacity: 0.3;
  }

  &::-webkit-resizer {
    background-repeat: no-repeat;
    width: 10px;
    height: 0;
  }

  &::-webkit-scrollbar {
    width: 10px;
    background-color: var(--white);
  }
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