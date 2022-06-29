<template>
<p>姓名：{{people.name}}年龄:{{people.age}}</p>
</template>

<script>
// 导入 ref 可以实现数据响应式修改
// import {ref} from 'vue'
// 导入 reactive 实现响应式数据
import { reactive } from 'vue'
export default{
  // 应用的入口
  setup(){
    // 直接定义数据 如果在 template 模板使用 需要 return 返回值
   // const 响应式数据 = reactive（数据初值）
   const people= reactive({name:'彭于晏',age:'23'})
    // 返回值
  return {
    people
  }
  }
}
</script>