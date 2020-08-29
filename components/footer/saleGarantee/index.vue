<template>
  <div class="col-3 px-1">
    <div class="d-flex flex-column align-items-center justify-content-center">
      <img :src="require('@/assets/image/' + imageName)">
      <span class="pt-2 text-center">{{ title }}</span>
    </div>
  </div>
</template>

<script>
    export default {
        name: "index",
      props:['title','imageName'],
    }
</script>

<style scoped>
  img{
    width: 50px;
  }
  span{
    color: rgba(0,0,0,0.5);
    font-size: 0.7rem;
    font-weight: bold;
  }
</style>
