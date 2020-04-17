<template>
  <div class="hello">
    
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
  }
}
</script>

