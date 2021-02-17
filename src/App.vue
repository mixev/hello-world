<template>
  <startPage />
</template>

<script>
import startPage from './components/startPage.vue'

export default {
  name: 'App',

  components: {
    startPage,
  },
}
</script>

<style>
html {
  height: 100%;
  margin: 0;
}
#app {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  height: 100%;
  display: flow-root;
}
.stpage {
  background-image: url('https://images.unsplash.com/photo-1593860572337-8face01d277e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1267&q=80');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100%;
  width: 100%;
  margin: 0;
  backdrop-filter: blur(8px);
}
.grad {
  height: 100vh;
  background: linear-gradient(rgba(255, 255, 255, 0.5), rgba(0, 0, 0, 0.5));
}
</style>
