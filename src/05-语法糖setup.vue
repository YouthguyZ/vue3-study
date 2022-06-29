<!-- script setup 语法糖用法 不用 return 返回值 -->
<script setup>
import {ref} from 'vue'
const user=ref({name:'老八',hobby:'football'})
const change=()=>{
  user.value.hobby='唱跳'
}
</script>

<template>
<p>{{user.name}},{{user.hobby}}</p>
<button @click="change">换个爱好</button>
</template>