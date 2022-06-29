<script setup>
// 函数过滤器 废弃 filter
import dayjs from 'dayjs'
const timeNow =Date.now();
const timeFormate = (time)=> {
  return dayjs(time).format('YYYY-MM-DD')
}

</script>

<template>
  {{timeFormate(timeNow)}}
</template>