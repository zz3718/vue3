<template>
  <div class="hello">
    HelloWord组件的object：{{object.user}}
    <!-- isRef: 判断一个变量是否是一个ref类型  -->

    <!-- toRefs:由于reactive初始化的数据没有get、set方法，所有需要转成ref类型 -->

    
  </div>
</template>

<script>
import { ref, reactive, isRef, toRefs } from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup() {
    const object = reactive({ 
      user: 'zhangsan' 
    })
    const countNum = ref(0)
    const unwrapped = isRef(countNum) ? countNum.value : countNum
    // console.log(unwrapped)
    console.log(object)
    const stateAsRefs = toRefs(object)
    console.log(stateAsRefs, '====')

    return {
      object
    }
  }
}
</script>

