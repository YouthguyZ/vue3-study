<!-- script setup 语法糖用法 不用 return 返回值 -->
<script setup>
// 导入
import {computed, ref} from 'vue'
// 定义响应式数据
const user=ref({name:'老八',hobby:'football',salary:'10000'})
const change=()=>{
  user.value.hobby='唱跳'
}

// 计算属性 根据原有的响应式数据进行修改 派生
const total =computed(()=>{
  // computed 里面要有返回值
  return user.value.salary*12
})
</script>

<template>
<p>{{user.name}},{{user.hobby}}年薪：{{total}}</p>
<button @click="change">换个爱好</button>
</template>