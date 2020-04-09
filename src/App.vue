<template>
  <div id="app">
    <Background src="wallhaven-512644.png" blur="5"/>
    <Logo title="Ke Wang"/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Background from './components/Background.vue'
import Logo from './components/Logo.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Background,
    Logo
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
