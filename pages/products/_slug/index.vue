<template>
  <div class="bg-gray col-12 d-flex flex-column px-2 px-md-5 py-4">
    <div class="d-flex">
      <div class="col-12 col-md-9 px-0 mt-3 mt-md-0">
        <div class="customShadow d-flex flex-column bg-white p-3">
          <div class="d-flex flex-column flex-md-row mb-3">
            <div class="col-12 col-md-6 d-flex border-left p-0" dir="ltr">
              <div class="w-100">
                <b-card no-body>
                  <b-tabs vertical end>
                    <b-tab v-for="item in productInfo.images">
                      <template v-slot:title>
                        <img :src="require('@/assets/image/' + item)">
                      </template>
                      <b-card-img :src="require('@/assets/image/' + item)"/>
                    </b-tab>
                  </b-tabs>
                </b-card>
              </div>
            </div>
            <div class="col-12 col-md-6 d-flex flex-column justify-content-between">
              <div>
                <div class="info d-flex flex-column align-items-start w-100 pb-2">
                  <h3 class="mb-4">{{$route.params.slug}}</h3>
                  <div class="d-flex flex-column">
                    <h4>برند : <span>{{productInfo.brand}}</span></h4>
                    <h4 class="mt-2">رنگ : <span>{{productInfo.color}}</span></h4>
                  </div>
                </div>
                <div class="d-flex flex-column mt-4 align-items-start">
                  <span class="mb-2">گارانتی : {{productInfo.garantee.name}}</span>
                  <span class="mb-2">شرایط گارانتی : {{productInfo.garantee.condition}}</span>
                  <span>خدمات پس از فروش : {{productInfo.garantee.saleService}}</span>
                </div>
                <div class="price d-flex flex-column justify-content-center">
                  <div class="d-flex mt-4 align-items-center">
                    <h4 class="mb-0">قیمت :  </h4>
                    <div v-if="productInfo.discount_price===0"><h5 class="mb-0 mr-2">{{productInfo.price}} تومان</h5></div>
                    <div class="d-flex align-items-center" v-else>
                      <span class="mx-2 ">{{productInfo.price}} تومان</span>
                      <h5 class="mb-0 mr-2 py-2 px-3">{{productInfo.discount_price}} تومان</h5>
                      </div>
                  </div>
                </div>
              </div>
              <div class="top d-flex justify-content-center border-top mt-4">
                <div class="d-flex justify-content-around pt-3 w-100">
                  <sale-garantee v-for="item in garantee"  :imageName="item.image" :title="item.title"/>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="d-flex flex-column col-12 col-md-3 p-0 pr-md-2 ">
        <div class="bg-white customShadow p-3 h-100">
          <div class="properties d-flex flex-column text-right">
            <p class="text-justify">لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی در صنعت چاپ، صفحه‌آرایی و طراحی گرافیک گفته می‌شود. طراح گرافیک از این متن به عنوان عنصری از ترکیب بندی برای پر کردن صفحه و ارایه اولیه شکل ظاهری و کلی طرح سفارش گرفته شده استفاده می نماید، تا از نظر گرافیکی نشانگر</p>
            <h4>ویژگی های محصول</h4>
            <ul class="pr-4">
              <li v-for="item in productInfo.properties">{{item}}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <!--    DESCRIPTION TABS   -->
    <div class="mt-3">
      <b-card no-body>
        <b-tabs card>
          <b-tab title="معرفی محصول" active>
            <b-card-text class="text-justify">لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی در صنعت چاپ، صفحه‌آرایی و طراحی گرافیک گفته می‌شود. طراح گرافیک از این متن به عنوان عنصری از ترکیب بندی برای پر کردن صفحه و ارایه اولیه شکل ظاهری و کلی طرح سفارش گرفته شده استفاده می نماید، تا از نظر گرافیکی نشانگر چگونگی نوع و اندازه فونت و ظاهر متن باشد. معمولا طراحان گرافیک برای صفحه‌آرایی، نخست از متن‌های آزمایشی و بی‌معنی استفاده می‌کنند تا صرفا به مشتری یا صاحب کار خود نشان دهند که صفحه طراحی یا صفحه بندی شده بعد از اینکه متن در آن قرار گیرد چگونه به نظر می‌رسد و قلم‌ها و اندازه‌بندی‌ها چگونه در نظر گرفته شده‌است. از آنجایی که طراحان عموما نویسنده متن نیستند و وظیفه رعایت حق تکثیر متون را ندارند و در همان حال کار آنها به نوعی وابسته به متن می‌باشد آنها با استفاده از محتویات ساختگی، صفحه گرافیکی خود را صفحه‌آرایی می‌کنند تا مرحله طراحی و صفحه‌بندی را به پایان برند</b-card-text>
          </b-tab>
          <b-tab title="مشخصات محصول">
            <b-card-text>
              <div class="d-flex">
                <div class="col-4">
                  <ul class="text-right pr-0">
                    <li class="py-2" v-for="item in productAttributes"><a href="#" class="my-2 py-2 px-1">{{item.name}}</a> </li>
                  </ul>
                </div>
                <div class="col-8">
                  <ul class="text-right pr-0">
                    <li class="py-2" v-for="item in productAttributes"><a href="#" class="my-2 py-2 px-1">{{item.value}}</a></li>
                  </ul>
                </div>
              </div>
            </b-card-text>
          </b-tab>
          <b-tab title="نظرات شما">
            <b-card-text>
              <div class="comment d-flex flex-column">
                <h4 class="mb-5 text-right">دیدگاه ها</h4>
                <div class="d-flex flex-column W-100" v-for="item in comments">
                  <CommentItem :comment="item"/>
                </div>
                <div class="d-flex flex-column align-items-start mb-2">
                  <b-form-rating id="rating-inline" variant="warning" no-border size="sm" inline value="4"></b-form-rating>
                </div>
                <h5 class="mb-3 text-right">شما هم می توانید در مورد این کالا نظر بدهید.</h5>
                <h5 class="font-weight-normal mb-3 text-right">جهت ثبت نظر، وارد وب سایت شوید.</h5>
                <form class="text-left w-50">
                  <input type="email" class="form-control form-control-sm" id="inputEmail4" placeholder="عنوان نظر خود را وارد کنید."/>
                  <input type="text" class="form-control form-control-sm my-3" id="inputAddress" placeholder="ایمیل خودرا وارد کنید."/>
                  <textarea class="form-control form-control-sm" id="exampleFormControlTextarea1" rows="4" placeholder="دیدگاه خود را وارد کنید"></textarea>
                  <button type="submit" class="btn bg-orange mt-3">ارسال</button>
                </form>
              </div>
            </b-card-text>
          </b-tab>
        </b-tabs>
      </b-card>
    </div>
    <!--    END OF DESCRIPTION TABS-->

    <!--    RELATED PRODUCTS   -->
    <div class="col-12 px-0 mt-3">
      <div class="customShadow d-flex flex-column bg-white p-4">
        <Title title=" محصولات مرتبط" show="true"/>
        <carousel  dir="ltr" navigationNextLabel="<i class='fa fa-angle-right'></i>" navigationPrevLabel="<i class='fa fa-angle-left'></i>" :perPageCustom="[[0, 1], [1024, 5]]" :pagination-enabled="true" :navigation-enabled="true">
          <slide v-for="item in products" :key="item.id" class="px-md-1">
            <Product :product="item" />
          </slide>
        </carousel>
      </div>
    </div>
    <!--    END OF RELATED PRODUCTS   -->

  </div>
</template>

<script>
  import RightSidebar from '@/components/rightSideBar'
  import CommentItem from '@/components/singlePage/commentItem'
  import SaleGarantee from '@/components/footer/saleGarantee'
  export default {
    name: "index",
    components:{
      RightSidebar,
      CommentItem,
      SaleGarantee
    },
    data() {
      return {
        productCategory: [
          {
            name:'کولر',
            subCategory:['آبی','گازی','ایستاده','تهویه مطبوع','گازی اسپلیت']
          },
          {
            name:'شوفاژ',
            subCategory:['شوفاژ پره ای','رادیاتور قرنیزی','رایاتور پنلی','رادیاتور پره ای']
          },
          {
            name:'بخاری',
            subCategory:['گازی','رادیاتور پره ای']
          }
        ],
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
        comments:[
          {
            product:'کولر آبی',
            name:'نام و نام خانوادگی',
            date:'3/4/99',
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. '
          },
          {
            product:'کولر آبی',
            name:'نام و نام خانوادگی',
            date:'3/4/99',
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. '
          },
          {
            product:'کولر آبی',
            name:'نام و نام خانوادگی',
            date:'3/4/99',
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. '
          },
        ],
        productInfo:{
          images:['pr1.png','pr2.png','pr3.png',],
          brand:'نام برند',
          color:'مشکی',
          price:'300000',
          discount_price:290000,
          Attributes:[
            {
              name:'حجم کولر',
              value:'2800'
            },
            {
              name:'میزان ورودی آب',
              value:'1/4 اینچ'
            },
            {
              name:'ولتاژ ورودی برق',
              value:'220'
            },
            {
              name:'قدرت پمپ',
              value:'6/1 HP'
            },
            {
              name:'قدرت موتور',
              value:'1/8 اسب بخار'
            },
          ],
          properties:[
            'عملکرد: سرمايش و گرمایش',
            'برای مساحت 55 تا 75 متر مربع (براساس شرایط)',
            'دارای فیلتر پلی پروپیلن و صفحه نمایش دیجیتال',
            'تنظیم اتومات پرتاب باد عمودی و افقی',
            'حداکثر فاصله افقی پنل داخلی با بیرونی: 30 متر',
            'قابلیت کارکرد در مناطق معتدل و حاره ای',
            'دارای گاز مبرد R410a و کمپرسور روتاری',
            'نصب رایگان',
          ],
          garantee:{
            name:'5 سال گارنتی شرکت اصلی',
            condition:'5 سال ضمانت كمپرسور و 18 ماه گارانتی قطعات فنی',
            saleService:'10 سال',
          }
        },
        garantee:[
          {
            title:'تضمین بهترین قیمت',
            image:'money.png',
          },
          {
            title:'ضمانت اصالت کالا',
            image:'certificate.png',
          },
          {
            title:'خدمات پس از فروش',
            image:'maintenance.png',
          },
          {
            title:'خرید اقساطی',
            image:'calculator.png',
          },
        ],
      }
    },
  }
</script>

<style lang="scss" scoped>
  .nav-link{
    background-color: #fff !important;
  }
  .nav-link img{
    opacity: 0.6;
    padding: 5px;
  }
  .nav-link img:hover{
    border: 1px solid #e0e0e0;
    opacity: 1;
  }
  .info {
    /* box-shadow: 0 3px 10px #e0e0e0; */
    border-bottom: 1px solid #e0e0e0;
  }
  .info h3{
    font-size: 1.3rem;
    color: $blue;
  }
  .info h4{
    font-size: 0.9rem;
    color: #000;
  }
  .info span{
    font-size: 0.9rem;
    color: rgb(87, 85, 85);
  }
  .color h4{
    color: #000;
    font-size: 1rem;
  }
  .color div{
    background-color: #000;
    width: 15px;
    height: 15px;
  }
  .color h5{
    color: #000;
    font-size: 1rem;
  }
  .price h4{
    font-size: 1rem;
  }
  .price h5{
    font-size: 1rem;
    font-weight: bold;
    color: #fff;
    background-color: $orange;
    border-top-right-radius: 6px;
    border-bottom-left-radius: 6px;
  }
  .price span{
    text-decoration: line-through;
    font-size: 0.9rem;
    color: #1b6a6f;
    font-weight: bold;
  }
  .properties p{
    color: rgba(0,0,0,0.6);
    font-size: 0.7rem;
  }
  .properties h4{
    font-size: 0.9rem;
  }
  .properties ul li{
    font-size: 0.7rem;
    list-style-type:circle;
    padding: 5px 0;
  }

  /* description */

  .desctab a{
    border-top-width: 2px !important;
    color: #000 !important;
  }
  .desctab a:focus , .desctab a:hover{
    border-top: 2px solid #1b6a6f !important;
  }

  .description{
    border: 1px solid #e0e0e0;
    border-top: 1px solid transparent !important;
  }

  .tab-pane p{
    color: rgba(0,0,0,0.7);
    line-height: 30px;
    padding: 10px 30px;
  }
  .tab-pane ul{
    list-style-type: none;
  }
  .tab-pane ul li{
    /* border-bottom: 1px solid #e0e0e0; */
    background-color:#f7f7f7;
    margin-bottom: 10px;
    padding-right: 10px;
  }
  .tab-pane ul li a{
    /* border-bottom: 1px solid #d7ac00; */
    color: rgb(109, 107, 107);
  }
  /* comment */
  .comment h4{
    font-size: 1.5rem;
  }
  .comment h5{
    font-size: 1rem;
  }
  .comment .star img{
    width: 20px;
  }

  .comment form {
    color:#000000 ;
  }
  .comment form input , textarea{
    /* background-color: #181616!important;
    border: 1px solid #367daf !important; */
  }
  .comment form label{
    font-size: 0.8rem;

  }
  .comment form button{
    font-size: 0.8rem !important;
    color: #fff !important;
    border-radius: 2px;
    padding: 5px 20px;
  }
  input , textarea{
    box-shadow: none !important;
    outline:none !important;
    border-radius: 2px;
    font-size: 0.8rem;
  }
</style>
<style lang="scss">
  .nav-tabs .nav-link{
    color:$title  !important;
  }
  .card{
    border: none !important;
  }
  .card .nav-link{
    border: none !important;
  }
  .card .nav-link img{
    width: 50px !important;
  }
  .card .nav-tabs{
    border: none !important;
  }
</style>
