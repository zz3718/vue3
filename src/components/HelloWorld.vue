<template>
  <div class="hello">
    HelloWord组件的object：{{object.user}}
  </div>
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup() {
    const object = reactive({ 
      user: 'zhangsan' 
    })

    return {
      object
    }
  }
}
</script>

