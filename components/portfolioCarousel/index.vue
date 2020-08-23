<template>
  <div class=" customCarousel position-relative" dir="ltr">
    <carousel :per-page="1" :pagination-enabled="false" :navigation-enabled="true">
      <slide v-for="photo in photos" :key="photo">
        <img :src="require('@/assets/img/' + photo)" class="w-100">
      </slide>
    </carousel>
    <div class="content position-absolute d-flex align-items-center justify-content-end">
      <p class="m-0 pr-3">{{title}}</p>
    </div>
    <div class="hover position-absolute d-flex align-items-center justify-content-start">
      <p class="m-0 pl-3">{{date}}</p>
    </div>
  </div>
</template>

<script>
    export default {
        name: "index",
        props:['title','date','photos']
    }
</script>

<style>
  .customCarousel img{
    border-radius: 2px;
  }
  .customCarousel .hover{
    background-color: rgba(0,0,0,0.5);
    z-index: 5;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 40px;
    opacity: 0;
  }
  .customCarousel .hover p{
    color: #fff;
    font-size: 0.8rem;
  }
  .customCarousel .content{
    bottom: 0;
    left: 0;
    width: 100%;
    height: 40px;
    color: #fff;
    z-index:6;
  }
  .customCarousel .VueCarousel-navigation-prev ,.customCarousel .VueCarousel-navigation-next{
    background-color: rgba(0,0,0,0.5) !important;
    transform: translateY(-50%) translateX(0%) !important;
    opacity: 0 !important;
    color: #fff !important;
    transition: all 0.3s ease-in-out;
    font-size: 0.8rem !important;
  }
  .customCarousel .hover{
    transition: all 0.3s ease-in-out;
  }
  .customCarousel:hover .hover , .customCarousel:hover .VueCarousel-navigation-prev, .customCarousel:hover .VueCarousel-navigation-next{
    opacity: 1 !important;
  }
</style>
