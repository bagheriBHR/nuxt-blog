<template>
  <div class="commentcard w-100 d-flex flex-column align-items-start p-3 mb-5">
    <h4 class="mb-3">{{comment.product}}</h4>
    <h5 class="mb-2 pb-2">توسط {{comment.name}} در تاریخ {{comment.date}}</h5>
    <p>{{comment.body}}</p>
  </div>
</template>

<script>
    export default {
        name: "index",
        props:['comment']
    }
</script>

<style lang="scss" scoped>
  .commentcard{
    border-right: 2px solid $orange !important;
    border: 1px solid rgba(0,0,0,0.1);
  }
  .commentcard h4{
    font-size: 0.9rem;
    color: rgb(98, 98, 98);
  }
  .commentcard h5{
    font-size: 0.8rem;
    border-bottom: 1px solid #e0e0e0;
    color: rgb(98, 98, 98);
  }
  .commentcard p{
    font-size: 0.8rem;
    color: rgb(138, 136, 136);
  }
</style>
