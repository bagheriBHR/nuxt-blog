<template>
  <div class="topitem2 d-flex flex-column align-items-center mt-3 mt-md-0 position-relative h-100">
    <img :src="require('@/assets/img/'+image)" class="w-100 h-100">
    <div class="hover position-absolute w-100 p-3">
      <h3>{{title}}</h3>
      <p class="mt-3 text-justify mb-0">
        {{body}}
      </p>
    </div>
    <div class="title position-absolute w-100 pr-3">
      <h3 class="mb-3 font-weight-bold">{{title}}</h3>
    </div>
  </div>
</template>

<script>
    export default {
        name: "index",
      props:['title','image','body','className']
    }
</script>

<style lang="scss" scoped>
  .topitem2{
    transition: all 0.3s;
    cursor: pointer;
    overflow: hidden;
    box-shadow: 0 0 7px rgba(0, 0, 0, 0.3);
  }
  .topitem2 h3 {
    font-size: 0.7rem;
  }
  .topitem2 p {
    font-size: 0.7rem;
  }
  .topitem2 .hover {
    top: 100%;
    color: #fff;
    text-align: center;
    transition: all 0.5s;
    z-index: 1;
    height: 100%;
  }
  .topitem2:hover .hover {
    top: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: rgba(0,0,0,0.5);
  }
  .topitem2:hover .title {
    opacity: 0;
  }
  .topitem2 .title{
    bottom: 0px;
    color: #fff;
    text-align: right;
    transition: all 0.6s;
  }
</style>
