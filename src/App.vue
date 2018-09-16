<template>
  <div id="app">
    <!-- 显示的是当前路由所对应内容 -->
    <router-view/>
  </div>
</template>

<script>
/**
 * 以vue结尾的文件叫做单文件组件
 * 模板放在template
 * 逻辑放在script文件里
 * 样式放在style里
 */
export default {
  name: 'App'
}
</script>

<style>

</style>
