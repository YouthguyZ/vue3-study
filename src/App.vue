<script setup>
import { ref } from 'vue';
import son from './components/son.vue'

const car=ref('GTR')
const changecar = () => {
  car.value=car.value
}
</script>

<template>
<p>父组件</p>
{{car}}
<son :car=car @changecar="changecar"/>
</template>