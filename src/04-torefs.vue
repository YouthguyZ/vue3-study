<template>
<p>姓名：{{name}},年龄:{{age}}</p>
<button @click="group">过年了</button>
</template>

<script>
// 导入 ref 可以实现数据响应式修改
// import {ref} from 'vue'
// 导入 reactive 实现响应式数据
import { reactive, toRefs } from 'vue'
// 导入 torefs 解决结构时 数据丢失的问题 结构数据 将每一个属性装换成用 ref包裹的响应式数据
import { toRef } from 'vue'
export default{
  // 应用的入口
  setup(){
    // 直接定义数据 如果在 template 模板使用 需要 return 返回值
   // const 响应式数据 = reactive（数据初值）
   const people= reactive({name:'彭于晏',age:23})
   let {name,age}=toRefs(people)
   const group=()=>{
    // 转换成 ref 后 方法属性 记得加 value
    age.value+=1
   }
    // 返回值
  return {
    people,
    name,
    age,
    group

  }
  }
}
</script>