<template>
  <div class="bg-gray col-12 d-flex flex-column flex-md-row px-2 px-md-5 py-4">
    <div class="d-flex flex-column col-12 col-md-2 p-0">
      <div  class="d-flex flex-column align-item-start w-100" v-for="item in attributeGroups" :key="item.title">
        <Sidebar :attributeGroup="item"/>
      </div>
    </div>
    <div class="col-12 col-md-10 px-0 pr-md-2 mt-3 mt-md-0">
      <div class="customShadow d-flex flex-column bg-white p-4">
        <Title title="دسته بندی محصول"/>
        <div class="d-flex flex-wrap mb-3">
          <div v-for="item in products" class="px-1 col-12 col-md-3 mt-2">
            <Product :product="item" />
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
    import Sidebar from '@/components/categorySideBar'
    export default {
        name: "index",
      data(){
          return{
            perPage: 5,
            currentPage: 1,
            products:[
              {
                id:'1',
                photo:'pr1.png',
                price:'1000000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount:'900000',
                name:'نام محصول'
              },
              {
                id:'2',
                photo:'pr2.png',
                price:'2500000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount:'1900000',
                name:'نام محصول'
              },
              {
                id:'3',
                photo:'pr3.png',
                price:'900000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount: '',
                name:'نام محصول'
              },
              {
                id:'4',
                photo:'pr1.png',
                price:'3000000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount:'2700000',
                name:'نام محصول'
              },
              {
                id:'5',
                photo:'pr1.png',
                price:'1000000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount:'900000',
                name:'نام محصول'
              },
              {
                id:'6',
                photo:'pr2.png',
                price:'2500000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount:'1900000',
                name:'نام محصول'
              },
              {
                id:'7',
                photo:'pr3.png',
                price:'900000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount: '',
                name:'نام محصول'
              },
              {
                id:'8',
                photo:'pr1.png',
                price:'3000000',
                content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
                discount:'2700000',
                name:'نام محصول'
              },
            ],
            attributeGroups:[
              {
                id:'1',
                title:'برند',
                attributeValues:['برند1','برند2','برند3','برند4','برند5','برند6','برند7','برند8','برند9','برند10','برند11',],
              },
              {
                id:'2',
                title:'قدرت موتور',
                attributeValues:['قدرت1','قدرت2','قدرت3','قدرت4','قدرت5','قدرت6'],
              },
              {
                id:'3',
                title:'رنگ',
                attributeValues:['آبی','سیاه','سفید','قهوه ای','قرمز','نارنجی','سبز'],
              },
              {
                id:'4',
                title:'محدوده قیمت',
                attributeValues:['محدوده1','محدوده2','محدوده3','محدوده4' ],
              }
            ],
          }
      },
      components:{
        Sidebar,
      },
      computed: {
        rows() {
          return this.products.length
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

