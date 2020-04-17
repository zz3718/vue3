<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    App.vue中的count：{{count}}
    <WatchEffect title="父组件传的值"/>
    <lifecycleHooks/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import WatchEffect from './components/watchEffect.vue'
import lifecycleHooks from './components/lifecycleHooks.vue'
import { ref } from 'vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    WatchEffect,
    lifecycleHooks
  },
  setup() {
    const count = ref(0)
    return {
      count
    }
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
