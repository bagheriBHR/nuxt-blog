<template>
  <div class="bg-gray col-12 p-0 d-flex flex-column flex-md-row px-2 px-md-5 py-4">
    <div class="col-12 col-md-2 p-0">
      <RightSidebar title="دسته بندی خدمات" :category="serviceCategory" @subItemClicked="subItem=$event"/>
    </div>
    <div class="col-12 col-md-10 px-0 pr-md-2 mt-3 mt-md-0">
      <div class="customShadow d-flex flex-column bg-white p-4">
        <Title :title="$route.params.slug==='all' ? 'تمامی خدمات' : $route.params.slug" :subItem="subItem"/>
        <div class="d-flex flex-wrap">
          <div class="col-12 col-md-3 mt-3" v-for="item in services" :key="item.id">
            <service-item :item="item"/>
          </div>
        </div>
      </div>
      <div class="d-flex justify-content-center py-3">
        <b-pagination
          v-model="currentPage"
          :total-rows="rows"
          :per-page="perPage"
          aria-controls="my-table"
        ></b-pagination>
      </div>
    </div>
  </div>
</template>

<script>
  import RightSidebar from '@/components/rightSideBar'
  import Title from '@/components/title'
  import ServiceItem from '@/components/serviceItem'
  export default {
    name: "index",
    data(){
      return{
        perPage: 5,
        currentPage: 1,
        services:[
          {
            photo:'service1.jpg',
            title:'تعمیر موتورخانه'
          },
          {
            photo:'service2.jpg',
            title:'لوله کشی ساختمان'
          },
          {
            photo:'service3.jpg',
            title:'حفر چاه'
          },
          {
            photo:'service4.jpg',
            title:'تعمیر شوفاژ'
          },
          {
            photo:'service1.jpg',
            title:'تعمیر موتورخانه'
          },
          {
            photo:'service2.jpg',
            title:'لوله کشی ساختمان'
          },
          {
            photo:'service3.jpg',
            title:'حفر چاه'
          },
          {
            photo:'service4.jpg',
            title:'تعمیر شوفاژ'
          },
        ],
        serviceCategory: [
          {
            id:'1',
            name:'تاسیساتی',
            slug:'تاسیساتی',
            parentId:null,
          },
          {
            id:'2',
            name:'حفر چاه',
            slug:'حفر چاه',
            parentId:null,
          },
          {
            id:'5',
            name:'تعمیر موتور خانه',
            slug:'تعمیر موتور خانه',
            parentId:'1',
          },
          {
            id:'3',
            name:'بهینه سازی سیستم آب',
            slug:'بهینه سازی سیستم آب',
            parentId:'1',
          },
          {
            id:'4',
            name:'تعویض موتور پمپ',
            slug:'تعویض موتور پمپ',
            parentId:'1',
          },
          {
            id:'6',
            name:'حفر چاه دستی',
            slug:'حفر چاه دستی',
            parentId:'2',
          },
          {
            id:'7',
            name:'حفر چاه با دستگاه',
            slug:'حفر چاه با دستگاه',
            parentId:'2',
          },
        ],
        subItem:''
      }
    },
    components:{
      RightSidebar,
      ServiceItem,
      Title
    },
    computed: {
      rows() {
        return this.services.length
      }
    }
  }
</script>
<style lang="scss">
  .page-item.active .page-link{
    background-color: $orange;
    border: $orange;
    color: #fff;
  }
  .page-item .page-link{
    outline: none;
    box-shadow: none;
    color: $orange;
  }
</style>

