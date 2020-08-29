<template>
  <li>
    <i class="fa fa-angle-left ml-1"></i>
    <nuxt-link :to="path + slug">
      <slot></slot>
    </nuxt-link>

  </li>
</template>

<script>
    export default {
        name: "index",
        props:['path','slug']
    }
</script>

<style scoped>
  li{
    text-align: right;
    list-style-type: none;
    margin-bottom: 10px;
  }
  li a{
    font-size: 0.8rem;
    color: rgba(0,0,0,0.5);
    text-decoration: none;
  }
</style>
