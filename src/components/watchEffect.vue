<template>
  <div class="hello">
    watchEffect组件的object：{{count}}
    <p>{{title}}</p>
  </div>
</template>

<script>
import { ref, reactive, isRef, toRefs, computed, watchEffect } from 'vue'
export default {
  name: '',
  props: {
      title: {
          type: String,
          default: ''
      }
  },
  setup() {
    //   基础用法：监听数据变化，数据变化可以更新视图
    const count = ref(0)
    watchEffect(() => {
        console.log(count.value)
    })
    setTimeout(() => {
        count.value++
    }, 1000)


    // 
    return {
      count
    }
  }
}
</script>

