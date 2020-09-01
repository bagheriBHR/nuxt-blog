<template>
  <div class="col-12 p-0 d-flex flex-column flex-md-row mt-4 px-2 px-md-5">
    <div class="col-12 col-md-2 p-0">
      <RightSidebar :title="title" :category="category" @subItemClicked="subItem=$event" @subItemClickedId="subItemId=$event"/>
    </div>
    <div class="col-12 col-md-10 px-0 pr-md-2 mt-3 mt-md-0">
      <div class="customShadow d-flex flex-column bg-white p-4">
        <Title :title="title" :subItem="subItem" show="true" :link="services ? 'services' : 'products/category'"/>
        <carousel v-if="services"  dir="ltr" navigationNextLabel="<i class='fa fa-angle-right'></i>" navigationPrevLabel="<i class='fa fa-angle-left'></i>" :perPageCustom="[[0, 1],[641, 2], [1024, 4]]" :pagination-enabled="true" :navigation-enabled="true">
          <slide v-for="item in services" :key="item.id" v-if="subItemId==='' || item.category_id===subItemId">
            <service-item :item="item"/>
          </slide>
        </carousel>
        <carousel v-if="products"  dir="ltr" navigationNextLabel="<i class='fa fa-angle-right'></i>" navigationPrevLabel="<i class='fa fa-angle-left'></i>" :perPageCustom="[[0, 1],[641, 2], [1024, 4]]" :pagination-enabled="true" :navigation-enabled="true">
          <slide v-for="item in products"  :key="item.id" class="px-md-1" v-if="subItemId==='' || item.category_id===subItemId">
            <Product :product="item" />
          </slide>
        </carousel>
      </div>
    </div>
  </div>
</template>

<script>
    import RightSidebar from '@/components/rightSideBar'
    import Title from '@/components/title'
    import ServiceItem from '@/components/serviceItem'
    import Product from '@/components/product'
    export default {
      name: "index",
      components:{
        RightSidebar,
        Title,
        ServiceItem,
        Product
      },
      data(){
        return{
          subItem:'all',
          subItemId:''
        }
      },
      props:['title','category','services','products'],
    }
</script>

<style scoped>

</style>
