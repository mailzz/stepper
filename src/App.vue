<template>
  <v-app>
    <v-main>
      <Stepper1/>
    </v-main>
  </v-app>
</template>

<script>
import Stepper1 from './components/Stepper1.vue'
export default {
  name: 'App',
  components: {
    Stepper1
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
