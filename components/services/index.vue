<template>
    <div class="servicepart bg-white d-flex flex-row px-3 py-4">
      <div class="col-9  d-flex flex-column text-right p-0 ml-2 ml-md-0">
        <h2>{{title}}</h2>
        <h6 class="m-0">{{content}}</h6>
      </div>
      <div class="col-3 p-0 w-100">
        <img  :src="require('@/assets/image/' + photo)" alt="" class="w-100"/>
      </div>
    </div>
</template>

<script>
    export default {
        name: "index",
        props:['title','content','photo']
    }
</script>

<style lang="scss"  scoped>
  .servicepart{
    border-radius: 2px;
    box-shadow:0px 5px 10px #d7d7d7;
    border-top: 2px solid $orange;
  }
  .servicepart h2{
    font-size: 0.9rem;
    color: $title;
  }
  .servicepart h6{
    font-size: 0.6rem;
    color: $p;
    line-height: 20px;
  }
</style>
