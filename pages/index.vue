<template>
  <div class="bg-gray d-flex flex-column">
<!--  CAROUSEL   -->
    <landing-page/>
<!--  END OF CAROUSEL   -->

<!--    TOP SERVICES   -->
    <div class="d-flex flex-column flex-md-row px-2 px-md-5 mt-3">
      <div class="service col-12 col-md-3 p-0 mt-2 mt-md-0" v-for="item in topServices" :key="item.title">
        <Service :title="item.title" :photo="item.photo" :content="item.content"/>
      </div>
    </div>
<!--    END OF TOP SERVICES   -->

<!--    PRODUCTS   -->
      <category-item
        title="جدیدترین محصولات"
        :category="productCategory"
        :products="products"
      />
<!--    END OF PRODUCTS   -->

<!--    services   -->
      <category-item
        title="خدمات"
        :category="serviceCategory"
        :services="services"
      />
<!--    end of services   -->

<!--    portfolio   -->
    <div class="customShadow d-flex flex-column mx-2 mx-md-5 bg-white p-4 my-4">
      <Title title="نمونه کار" show="true" link="portfolio"/>
      <div class="d-flex flex-wrap mb-4">
        <div class="col-12 col-md-3 mt-4" v-for="item in portfolio" :key="item.id">
          <portfolioCarousel :portfolioItem="item"/>
        </div>
      </div>
    </div>
<!--    end of portfolio  -->

<!--    ABOUT US   -->
    <div class="about px-2 px-md-5 mt-4">
      <div class="d-flex flex-column align-items-start py-5">
        <div class="d-flex flex-column flex-md-row">
          <div class="col-12 col-md-8 d-flex flex-column align-items-start mb-3">
            <h2 class="mb-3">درباره ما</h2>
            <p class="text-justify mb-0">لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی در صنعت چاپ، صفحه‌آرایی و طراحی گرافیک گفته می‌شود. طراح گرافیک از این متن به عنوان عنصری از ترکیب بندی برای پر کردن صفحه و ارایه اولیه شکل ظاهری و کلی طرح سفارش گرفته شده استفاده می نماید، تا از نظر گرافیکی نشانگر چگونگی نوع و اندازه فونت و ظاهر متن باشد. معمولا طراحان گرافیک برای صفحه‌آرایی، نخست از متن‌های آزمایشی و بی‌معنی استفاده می‌کنند تا صرفا به مشتری یا صاحب کار خود نشان دهند که صفحه طراحی یا صفحه بندی شده بعد از اینکه متن در آن قرار گیرد چگونه به نظر می‌رسد و قلم‌ها و اندازه‌بندی‌ها چگونه در نظر گرفته شده‌است. از آنجایی که طراحان عموما نویسنده متن نیستند و وظیفه رعایت حق تکثیر متون را ندارند و در همان حال کار آنها به نوعی وابسته به متن می‌باشد آنها با استفاده از محتویات ساختگی، صفحه گرافیکی خود را صفحه‌آرایی می‌کنند تا مرحله طراحی و صفحه‌بندی را به پایان برند.</p>
            <button class="btn bg-orange px-4 py-1 mt-4">
              <router-link to="/aboutUs" class="text-decoration-none text-white ">ادامه مطلب</router-link>
            </button>
          </div>
          <div class="d-none d-md-block col-md-4 ">
            <div class="img_container d-flex align-items-center justify-content-center h-100">
              <img src="@/assets/image/logo.png" >
            </div>
          </div>
        </div>
        <div class="d-flex flex-column align-items-center mt-3">
          <h2 class="title2 position-relative">تیم ما</h2>
          <div class="d-flex flex-wrap align-items-center justify-content-center mx-2 mx-md-5">
            <TeamItem v-for="item in employees" :employee="item"/>
          </div>
        </div>
      </div>
    </div>
<!--    END OF ABOUT US  -->

<!--    COMMENTS   -->
    <div class="col-12 d-flex flex-column px-4 px-md-5 py-5">
      <div class="d-flex justify-content-center w-100">
        <h2 class="commentTitle mb-5 position-relative">نظرات شما</h2>
      </div>
      <carousel :rtl="true" navigationNextLabel="<i class='fa fa-angle-right'></i>" navigationPrevLabel="<i class='fa fa-angle-left'></i>" :perPageCustom="[[0, 1],[641, 2], [1024, 3]]" :pagination-enabled="true" :navigation-enabled="true">
        <slide v-for="item in comments" :key="item.id">
          <CommentItem :comment="item"/>
        </slide>
      </carousel>
    </div>
<!--    END OF COMMENTS  -->
  </div>
</template>

<script>
  import LandingPage from '@/components/landingPage'
  import Service from '@/components/services'
  import portfolioCarousel from '@/components/portfolioCarousel'
  import TeamItem from '@/components/aboutUsTeamItem'
  import CommentItem from '@/components/commentItem'
  import Title from '@/components/title'
  import CategoryItem from '@/components/mainPageCategoryItem'
  export default {
    components:{
      LandingPage,
      Service,
      portfolioCarousel,
      TeamItem,
      CommentItem,
      Title,
      CategoryItem
    },
    data() {
      return {
        topServices:[
          {
            title:'مشاوره',
            content:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از',
            photo:'support.png'
          },
          {
            title:'فروش محصول',
            content:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از',
            photo:'shoppingicon.png'
          },
          {
            title:'نصب و نهداری',
            content:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از',
            photo:'maintenance.png'
          },
          {
            title:'تعمیر و تعویض قطعات',
            content:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از',
            photo:'maintenance2.png'
          }
        ],
        products:[
          {
            id:'1',
            photo:'pr1.png',
            price:'1000000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount:'900000',
            name:'نام محصول 1',
            slug:'نام محصول 1',
            category_id:'3',
          },
          {
            id:'2',
            photo:'pr2.png',
            price:'2500000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount:'1900000',
            name:'نام محصول 2',
            slug:'نام محصول 2',
            category_id:'3',
          },
          {
            id:'3',
            photo:'pr3.png',
            price:'900000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount: '',
            name:'نام محصول 3',
            slug:'نام محصول 3',
            category_id:'4',
          },
          {
            id:'4',
            photo:'pr1.png',
            price:'3000000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount:'2700000',
            name:'نام محصول 4',
            slug:'نام محصول 4',
            category_id:'4',
          },
          {
            id:'5',
            photo:'pr1.png',
            price:'1000000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount:'900000',
            name:'نام محصول 1',
            slug:'نام محصول 1',
            category_id:'5',
          },
          {
            id:'6',
            photo:'pr2.png',
            price:'2500000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount:'1900000',
            name:'نام محصول 2',
            slug:'نام محصول 2',
            category_id:'7',
          },
          {
            id:'7',
            photo:'pr3.png',
            price:'900000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount: '',
            name:'نام محصول 3',
            slug:'نام محصول 3',
            category_id:'7',
          },
          {
            id:'8',
            photo:'pr1.png',
            price:'3000000',
            content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
            discount:'2700000',
            name:'نام محصول 4',
            slug:'نام محصول 4',
            category_id:'8',
          },
        ],
        services:[
          {
            photo:'service1.jpg',
            title:'تعمیر موتورخانه',
            slug:'تعمیر موتورخانه',
            category_id:'5'
          },
          {
            photo:'service2.jpg',
            title:'لوله کشی ساختمان',
            slug:'لوله کشی ساختمان',
            category_id:'4'
          },
          {
            photo:'service3.jpg',
            title:'حفر چاه',
            slug:'حفر چاه',
            category_id:'6'
          },
          {
            photo:'service4.jpg',
            title:'تعمیر شوفاژ',
            slug:'تعمیر شوفاژ',
            category_id:'3'
          },
        ],
        productCategory: [
          {
            id:'1',
            name:'کولر',
            slug:'کولر',
            parentId:null,
          },
          {
            id:'2',
            name:'شوفاژ',
            slug:'شوفاژ',
            parentId:null,
          },
          {
            id:'3',
            name:'کولرآبی',
            slug:'کولرآبی',
            parentId:'1',
          },
          {
            id:'4',
            name:'کولر گازی',
            slug:'کولر گازی',
            parentId:'1',
          },
          {
            id:'5',
            name:'کولر ایستاده',
            slug:'کولر ایستاده',
            parentId:'1',
          },
          {
            id:'7',
            name:'شوفاژ پره ای',
            slug:'شوفاژ پره ای',
            parentId:'2',
          },
          {
            id:'8',
            name:'رادیاتور قرنیزی',
            slug:'رادیاتور قرنیزی',
            parentId:'2',
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
            slug:'حفر-چاه',
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
        portfolio: [
          {
            id:'1',
            title: 'تعمیر شوفاژ',
            slug: 'تعمیر-شوفاژ',
            photos:['service42.jpg','service4.jpg'],
            date:'3/4/99'
          },
          {
            id:'2',
            title: 'حفر چاه',
            slug: 'حفر-چاه',
            photos:['service32.jpg','service3.jpg'],
            date:'3/4/99'
          },
          {
            id:'3',
            title: 'لوله کشی ساختمان',
            slug: 'لوله-کشی-ساختمان',
            photos:['service22.jpg','service2.jpg'],
            date:'3/4/99'
          },
          {
            id:'4',
            title: 'تعمیر موتور',
            slug: 'تعمیر-موتور',
            photos:['service12.jpg','service1.jpg'],
            date:'3/4/99'
          },
          {
            id:'5',
            title: 'تعمیر شوفاژ',
            slug: 'تعمیر-شوفاژ',
            photos:['service42.jpg','service4.jpg'],
            date:'3/4/99'
          },
          {
            id:'6',
            title: 'حفر چاه',
            slug: 'حفر-چاه',
            photos:['service32.jpg','service3.jpg'],
            date:'3/4/99'
          },
          {
            id:'7',
            title: 'لوله کشی ساختمان',
            slug: 'لوله-کشی-ساختمان',
            photos:['service22.jpg','service2.jpg'],
            date:'3/4/99'
          },
          {
            id:'8',
            title: 'تعمیر موتور',
            slug: 'تعمیر-موتور',
            photos:['service12.jpg','service1.jpg'],
            date:'3/4/99'
          },
        ],
        comments:[
          {
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و می باشد.',
            name:'نام و نام خانوادگی',
            job:'موقعیت شغلی',
            photo:'profile4.jpg',
            id:'1'
          },
          {
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و می باشد.',
            name:'نام و نام خانوادگی',
            job:'موقعیت شغلی',
            photo:'profile3.jpg',
            id:'3'
          },
          {
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و می باشد.',
            name:'نام و نام خانوادگی',
            job:'موقعیت شغلی',
            photo:'profile2.jpg',
            id:'2'
          },
          {
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و می باشد.',
            name:'نام و نام خانوادگی',
            job:'موقعیت شغلی',
            photo:'profile2.jpg',
            id:'5'
          },
          {
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و می باشد.',
            name:'نام و نام خانوادگی',
            job:'موقعیت شغلی',
            photo:'profile4.jpg',
            id:'4'
          },
          {
            body:'لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و می باشد.',
            name:'نام و نام خانوادگی',
            job:'موقعیت شغلی',
            photo:'profile3.jpg',
            id:'6'
          },
        ],
        employees:[
          {
            id:'1',
            name:'نام و نام خانوادگی',
            post:'مدیریت',
            photo:'team1.jpg',
            socials:[
              {
                name:'telegram',
                value:'@telegram'
              },
              {
                name:'whatsapp',
                value:'whatsapp address'
              },
              {
                name:'instagram',
                value:'instagram address'
              },
              {
                name:'phone',
                value:'09216576633'
              },
            ]
          },
          {
            id:'2',
            name:'نام و نام خانوادگی',
            post:'طراح',
            photo:'team2.jpg',
            socials:[
              {
                name:'telegram',
                value:'@telegram'
              },
              {
                name:'whatsapp',
                value:'whatsapp address'
              },
              {
                name:'instagram',
                value:'instagram address'
              },
              {
                name:'phone',
                value:'09216576633'
              },
            ]
          },
          {
            id:'3',
            name:'نام و نام خانوادگی',
            post:'حسابدار',
            photo:'team3.jpg',
            socials:[
              {
                name:'telegram',
                value:'@telegram'
              },
              {
                name:'whatsapp',
                value:'whatsapp address'
              },
              {
                name:'instagram',
                value:'instagram address'
              },
              {
                name:'phone',
                value:'09216576633'
              },
            ]
          },
          {
            id:'4',
            name:'نام و نام خانوادگی',
            post:'مشاور',
            photo:'team4.jpg',
            socials:[
              {
                name:'telegram',
                value:'@telegram'
              },
              {
                name:'whatsapp',
                value:'whatsapp address'
              },
              {
                name:'instagram',
                value:'instagram address'
              },
              {
                name:'phone',
                value:'09216576633'
              },
            ]
          },
        ]
      }
    },
    methods:{
    }
  }
</script>

<style lang="scss" scoped>
  @media (min-width: 600px) {
    .service:first-child{
      padding-right: 0px !important;
    }
    .service{
      padding-right:10px !important;
    }
  }
  .about{
    background-color: #f8f8f8;
  }
  .about h2 , .title2{
    font-size: 1.1rem;
    color: $title;
  }
  .about p{
    line-height: 25px;
    color: $p;
  }
  .about img{
    width: 200px;
    border: 1px solid $blue;
  }
  .about button{
    font-size: 0.7rem;
    border-radius: 2px;
  }
  .title2:after ,.title2:before , .commentTitle:after , .commentTitle:before {
    content: " ";
    height: 0.1rem;
    width: 60px;
    background-color: $blue;
    position: absolute;
    top: 10px;
  }
  .title2:after {
    left: 60px;
  }
  .title2:before {
    right: 60px;
  }
  .commentTitle:after {
    left: 95px;
  }
  .commentTitle:before {
    right: 95px;
  }
  .commentBG{
    /*background: url("~assets/image/commentBG.jpg");*/
    background-size: cover;
    background-repeat: no-repeat;
  }
  .commentTitle{
    font-size: 1.2rem;
    color: $title;
  }

</style>
<style lang="scss">
  .VueCarousel-navigation-button{
    color: $blue !important;
    font-size: 1.5rem;
    font-weight: bold;
  }
  .VueCarousel-dot{
    width: 8px !important;
    height: 8px !important;
    outline: none !important;
    box-shadow: none !important;
  }
  .VueCarousel-dot--active{
    background-color: rgba(0,0,0,0.4) !important;
  }
  .customShadow{
    box-shadow: 0 0 3px rgba(0,0,0,0.1);
  }
  .VueCarousel-wrapper {
    padding-bottom: 15px !important;
  }
</style>
