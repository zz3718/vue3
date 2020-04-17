<template>
  <div class="hello">
    <button @click="emitClick()">向父组件传值</button>
  </div>
</template>

<script>
import { onMounted, onUpdated, onUnmounted, onBeforeMount } from 'vue'
export default {
  name: '',
  setup() {
      onBeforeMount(() => {
          console.log('onBeforeMount')
      })
    onMounted(() => {
      console.log('mounted!')
    })
    onUpdated(() => {
      console.log('updated!')
    })
    onUnmounted(() => {
      console.log('unmounted!')
    })

    function emitClick() {
        console.log('pppp')
        this.$emit('handle', '传出去的值')
    }
    return {
        emitClick
    }
  }
}
</script>

