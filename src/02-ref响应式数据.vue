<template>
<p>{{star.name}}{{star.say}}</p>
<button @click="skill">技能</button>
<hr>
 
</template>

<script>
// 导入 ref 可以实现数据响应式修改
import {ref} from 'vue'
export default{
  // 应用的入口
  setup(){
    // 直接定义数据 如果在 template 模板使用 需要 return 返回值
    const star=ref({name:'陈冠希',say:'hahaha'})
    // 定义方法
    const skill=()=>{
      star.value.say='wuwuuw~'
    }
    // 返回值
  return {
    star,
    skill
  }
  }
}
</script>