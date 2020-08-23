<template>
  <li>
    <i class="fa fa-angle-left ml-1"></i>
    <span class="mb-1">{{ title }}</span>
  </li>
</template>

<script>
    export default {
        name: "index",
        props:['title']
    }
</script>

<style scoped>
  li{
    font-size: 0.8rem;
    color: rgba(0,0,0,0.5);
    text-align: right;
    list-style-type: none;
    margin-bottom: 10px;
  }
</style>
