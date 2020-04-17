<template>
  <div class="hello">
    HelloWord组件的object：{{object.user}}
    <!-- isRef: 判断一个变量是否是一个ref类型  -->

    <!-- toRefs:由于reactive初始化的数据没有get、set方法，所有需要转成ref类型 -->

    <!-- computed -->
    <!-- computed:{{}} -->
    <!-- 
      总结：vue2.x与vue3.x的computed
      总的来说这两点和Vue2.x相同。
      唯一不同的是，3.0中，computed 被抽成一个API，直接从vue中获取，
      而Vue2.x中，computed是一个对象，在对象中定义一个个computed
     -->
  </div>
</template>

<script>
import { ref, reactive, isRef, toRefs, computed } from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup() {
    const object = reactive({ 
      user: 'zhangsan' 
    })
    const countNum = ref(4)
    const unwrapped = isRef(countNum) ? countNum.value : countNum
    // console.log(unwrapped)
    // console.log(object)
    const stateAsRefs = toRefs(object)
    // console.log(stateAsRefs, '====')

    // computed
    const plusOne = computed(() => countNum.value + 1)
    // console.log(plusOne)
    plusOne.value++; // reactivity.esm-bundler.js?a1e9:694 Write operation failed: computed value is readonly

    // 在调用 computed() 函数期间，传入一个包含 get 和 set 函数的对象，可以得到一个可读可写的计算属性，示例代码如下：
    const plusTwo = computed({
      get: () => {
        // console.log('get')
        countNum.value + 1
      },
      set: (val) => {
        // console.log('set')
        // console.log(val, '==val')
        countNum.value = val + 11
      }
    })
    plusTwo.value = 1;
    // console.log(countNum.value); // 0

    return {
      object
    }
  }
}
</script>

