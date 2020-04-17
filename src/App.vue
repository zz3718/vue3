<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    App.vue中的count：{{count}}
    <WatchEffect title="父组件传的值"/>
    <lifecycleHooks @handle="handleClick"/>
   自组件传来的值： {{val1}}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import WatchEffect from './components/watchEffect.vue'
import lifecycleHooks from './components/lifecycleHooks.vue'
import { ref, reactive } from 'vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    WatchEffect,
    lifecycleHooks
  },
  setup() {
    const count = ref(0)
    let val1 = ref('')
    let vals = reactive({
      name: 'zhansgan'
    })
    function handleClick(val) {
      val1.value = val
      console.log(val1)
      console.log(vals)
    }
    return {
      count,
      handleClick,
      val1
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
