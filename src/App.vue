<script setup>
import { ref,provide } from 'vue';

provide('car')

const user=ref({name:'tom',age:20})
</script>

<template>
{{user.name}}
</template>