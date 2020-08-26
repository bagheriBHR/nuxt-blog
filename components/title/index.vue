<template>
  <div class="col-12 d-flex p-0 mb-3 line position-relative d-flex justify-content-between">
      <h2 class="title pb-2 m-0 text-right position-relative pl-5">
        {{title}}
      <span v-if="subItem">( {{subItem}} )</span>
      </h2>
      <div v-if="show"><a> نمایش همه</a></div>
  </div>
</template>

<script>
    export default {
        name: "index",
        props:['title','show','subItem']
    }
</script>

<style lang="scss" scoped>
  .title{
    font-size: 1rem;
    color: $title;
  }
  .title:after{
    content: " ";
    position: absolute;
    width: 100%;
    height: 1px;
    background-color: $orange;
    right: 0;
    bottom: 0;
  }
  .title:before{
    content: " ";
    position: absolute;
    width: 15px;
    height: 1px;
    background-color: #fff;
    left: -15px;
    bottom: 0;
  }
  a{
    cursor: pointer;
    color: $title;
    text-decoration: none;
  }
  a:after{
    content: "\f104";
    font-family: FontAwesome;
    margin-right: 5px;
    font-size: 12px;
    color: #413d77;
  }
  .line:before{
    content: " ";
    position: absolute;
    width: 100%;
    height: 1px;
    background-color: rgba(0,0,0,0.2);
    right: 0;
    bottom: 0;
  }
</style>
