<template>
  <div class="mx-2 d-flex flex-column mt-4 mt-md-0">
    <div class="img_container">
      <nuxt-link :to="`/services/${item.slug}`">
        <img  :src="require('@/assets/img/' + item.photo)" class="w-100">
      </nuxt-link>
    </div>
    <div class="title text-center p-1 mt-2">
      <h6 class="w-100 m-0 p-2">{{item.title}}</h6>
    </div>
  </div>
</template>

<script>
    export default {
        name: "index",
        props:['item']
    }
</script>

<style lang="scss" scoped>
  .img_container{
    box-shadow: 0 0 7px rgba(0,0,0,0.4);
    border-radius: 2px;
    overflow: hidden;
  }
  .title{
    background-color: #949496;
  }
  .title h6{
    border: 1px solid rgba(255,255,255,0.2);
    color: #fff;
    font-weight: bold;
    font-size: 0.8rem;
    border-radius: 0;
  }
</style>
