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
// 默认时是get 属性
// const total =computed(()=>{
//   // computed 里面要有返回值
//   return user.value.salary*12
// })

// 计算属性高阶写法 对象里面两个参数 get set 
const total=computed({
  // 获取数据时 get
  get(){
    return user.value.salary*12
  },
  // 修改数据时才会用 set
  set(value){
    console.log(value);
   user.value.salary= value/12
  }
})
</script>

<template>
<p>{{user.name}},{{user.hobby}}年薪：{{total}}月薪：{{user.salary}}</p>
<button @click="change">换个爱好</button><br>
<label for="">输入</label><input v-model="total" type="text"/>
</template>