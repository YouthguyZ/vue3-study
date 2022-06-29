<!-- script setup 语法糖用法 不用 return 返回值 -->
<script setup>
// 导入
import {watch, ref} from 'vue'

// 定义数据
const user=ref({name:'菜鸡',age:22})

const change=()=>{
  user.value.age+=1
}

// watch 侦听属性
// 三个参数 
// 第一个参数 为侦听到的 对象、数组的响应式数据、函数返回值的响应式变化
// 第二个参数 为回调函数 第一个参数为改变后的新值、第二个参数为改变前的旧值
// 第三个参数 一个对象 为配置选项 immediate 立即地、deep：深度侦听 默认都是 false
// 开启深度侦听之后 第二个参数回调函数里的 oldvalue 与 newvalue 会是同一个值 都是改变后的新值
watch(user.value,(value,params)=>{
  console.log(value,params);
  console.log('call change');
},{immediate:true,deep:true})

</script>

<template>
<p>姓名：{{user.name}}=>年龄:{{user.age}}</p>
<button @click="change">改变</button>
</template>