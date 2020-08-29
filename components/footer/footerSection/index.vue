<template>
  <div class="footer_part col-12 col-md-6 d-flex flex-column">
    <h2 class="part_title">{{title}}</h2>
    <ul class="p-0">
      <Li v-for="item in items" :slug="item.slug" :path="item.path">
        {{item.name}}
      </Li>
    </ul>
  </div>
</template>

<script>
    import Li from '@/components/footer/li'
    export default {
      name: "index",
      props:['items','title'],
      components:{
        Li
      }
    }
</script>

<style scoped>
  .part_title{
    font-size: 0.9rem !important;
    color: rgba(0,0,0,0.6);
    text-align: right;
    margin-bottom: 20px;
    padding-bottom: 10px;
    font-weight: bold;
    border-bottom: 1px solid rgba(0,0,0,0.1);
  }
</style>
