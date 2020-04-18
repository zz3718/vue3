<template>
  <div class="hello">
    <button @click="emitClick()">向父组件传值</button>
    <p><button @click="getList()">获取数据</button></p>
  </div>
</template>

<script>
import { onMounted, onUpdated, onUnmounted, onBeforeMount } from 'vue'
import axios from 'axios'
export default {
  name: '',
  setup() {
      onBeforeMount(() => {
          console.log('onBeforeMount')
      })
    onMounted(() => {
      console.log('mounted!')
      getData()
    })
    onUpdated(() => {
      console.log('updated!')
    })
    onUnmounted(() => {
      console.log('unmounted!')
    })
    function getData() {
      axios.get('http://jsonplaceholder.typicode.com/users').then(res => {
        console.log(res.data)
      })
    }
    function getList() {
      axios.get('http://jsonplaceholder.typicode.com/users').then(res => {
        console.log(res.data)
      })
    }
    function emitClick() {
        console.log('pppp')
        this.$emit('handle', '传出去的值')
    }
    return {
        emitClick,
        getList
    }
  }
}
</script>

