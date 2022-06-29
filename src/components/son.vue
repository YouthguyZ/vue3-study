<script setup>
// 接收父组件传值
defineProps({
  car:{
    type:String
  }
})

// 子向父传值
const emit= defineEmits(['changecar'])
const change=()=>{
  emit('changecar','BEN-Z')

}
</script>

<template>
<h1>son组件</h1>
<p>传过来的：{{car}}</p>
<button @click="changecar">换车</button>
</template>