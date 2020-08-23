<template>
  <div class="comment d-flex flex-column align-items-center justify-content-center mx-2" dir="rtl">
    <div class="profile d-flex-justify-content-center align-items-center rounded-circle">
      <img :src="require('@/assets/img/' + comment.photo)" alt="" class="w-100 rounded-circle">
    </div>
    <h5 class="font-weight-bold my-3">{{comment.name}}</h5>
    <h4 class="">{{comment.job}}</h4>
    <div class="body d-flex justify-content-center align-items-center">
      <div class="position-relative d-flex align-items-center">
        <p class="text-justify m-0 px-3 position-relative">{{comment.body}}</p>
        <div class="border position-absolute"></div>
      </div>
    </div>
  </div>
</template>

<script>
    export default {
        name: "index",
        props:['comment']
    }
</script>

<style lang="scss" scoped>
  .profile{
    width: 100px;
    height: 100px;
    box-shadow: 0 0 4px rgba(0,0,0,0.2);
    padding:3px;
  }
  .border{
    background-color: $orange;
    padding: 1px;
    height: 30px;
    right: 0;
  }
  .body p{
    font-size: 0.7rem;
    line-height: 25px;
    color: $title;
    border-right: 3px solid #fff;
  }
  .comment h5{
    font-size: 0.9rem;
    color: $title;
  }
  .comment h4{
    font-size: 0.8rem;
    color: $p;
  }
</style>
