<template>
    <div id="footer">
      <div class="bg-footer d-flex flex-column">
        <div class="top d-flex justify-content-center p-3">
          <div class="col-12 col-md-8 d-flex">
            <sale-garantee v-for="item in garantee"  :imageName="item.image" :title="item.title"/>
          </div>
        </div>

        <div class="d-flex flex-column flex-md-row">
          <div class="col-12 col-md-4 d-flex flex-column flex-md-row mt-4">
            <footer-section title="اطلاعات" :items="info" />
            <footer-section title="جدیدترین محصولات" :items="products" path="/products/"/>
          </div>

          <div class="contact_part col-12 col-md-4 d-flex align-items-center position-relative">
            <div class="d-flex flex-column p-3">
              <div class="d-flex">
                <i class="fa fa-map-marker ml-3"></i>
                <p class="text-justify">{{websiteInfo.address}}</p>
              </div>
              <div class="d-flex">
                <i class="fa fa-phone ml-3"></i>
                <p class="text-justify">تلفن : {{websiteInfo.phone}}</p>
              </div>
              <div class="d-flex">
                <i class="fa fa-envelope ml-3"></i>
                <p class="text-justify mb-0">ایمیل : {{websiteInfo.email}}</p>
              </div>
              <div class="d-flex align-items-center justify-content-center mt-4">
                <a v-for="item in websiteInfo.socials" :href="item.src" class="follow d-flex align-items-center justify-content-center mx-2">
                  <i :class="`fa fa-${item.icon}`"></i>
                </a>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-4 d-flex flex-column justify-content-center align-items-center my-4 my-md-0">
            <div class="input-group pr-2 ">
              <div class="input-group-prepend">
                <a class="input-group-text">ارسال</a>
              </div>
              <input type="text" class="form-control text-right py-0" id="basic-url" aria-describedby="basic-addon3" placeholder="لطفا ایمیل خود را وارد کنید"/>
              <span class="d-flex align-items-center "><h5 class="font-weight-light px-2 m-0">عضویت در خبرنامه</h5></span>
            </div>
            <div class="electronic_symbol d-flex justify-content-center mt-4 mt-md-5">
              <img src="@/assets/image/trusticon.png" class="mx-3">
              <img src="@/assets/image/trusticon2.png" class="mx-3">
              <img src="@/assets/image/trusticon3.png" class="mx-3">
            </div>
          </div>
        </div>
      </div>
      <div class="footer_end d-flex flex-column align-items-center justify-content-center py-4 px-3">
        <p class="text-center m-0">تمامي كالاها و خدمات اين فروشگاه، داراي مجوزهاي لازم از مراجع مربوطه و فعاليت‌هاي اين سايت تابع قوانين و مقررات جمهوري اسلامي ايران است.</p>
      </div>
    </div>
</template>

<script>
    import SaleGarantee from './saleGarantee'
    import FooterSection from './footerSection'
    export default {
        name: "index",
        components:{
          SaleGarantee,
          FooterSection
      },
      data() {
        return {
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
          products:[
            {
              id:'1',
              photo:'pr1.png',
              price:'1000000',
              content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
              discount:'900000',
              name:'نام محصول 1',
              slug:'نام محصول 1'
            },
            {
              id:'2',
              photo:'pr2.png',
              price:'2500000',
              content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
              discount:'1900000',
              name:'نام محصول 2',
              slug:'نام محصول 2'
            },
            {
              id:'3',
              photo:'pr3.png',
              price:'900000',
              content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
              discount: '',
              name:'نام محصول 3',
              slug:'نام محصول 3'
            },
            {
              id:'4',
              photo:'pr1.png',
              price:'3000000',
              content:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی ',
              discount:'2700000',
              name:'نام محصول 4',
              slug:'نام محصول 4'
            },
          ],
          info:[
            {
              name:'بلاگ',
              src:'#',
              slug:'بلاگ'
            },
            {
              name:'خدمات پس از فروش',
              src:'#',
              slug:'خدمات-پس-از-فروش'
            },
            {
              name:'سوالات متداول',
              src:'#',
              slug:'سوالات-متداول'
            },
          ],
          websiteInfo:{
            name:'نام وب سایت',
            logoImg:'logo.png',
            email:'info@mysite.com\n',
            phone:'989132924768+',
            address:'لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی در صنعت چاپ، صفحه‌آرایی و طراحی گرافیک',
            socials:[
              {
                src:'#',
                icon:'telegram'
              },
              {
                src:'#',
                icon:'instagram'
              },
              {
                src:'#',
                icon:'whatsapp'
              },
              {
                src:'#',
                icon:'twitter'
              },
              {
                src:'#',
                icon:'facebook'
              },
            ]
          }
        }
      }
    }
</script>

<style lang="scss" scoped>
  .top{
    background-color: #d6d6d6;
    box-shadow: 0 1px 2px rgba(0,0,0,0.1);
  }
  .contact_part{
    box-shadow: 0 6px 8px rgba(0,0,0,0.2);
    background: $orange;
  }
  .contact_part div:nth-child(2){
    z-index: 3;
  }
  .pattern{
    background-repeat: repeat;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    opacity: 0.05;
    z-index: 1;
  }
  .contact_part i{
    color:rgba(0,0,0,0.6);
    font-size: 1.1rem;
    font-weight: bold;
  }
  .contact_part p{
    color:rgba(0,0,0,0.7);
    font-size: 0.8rem;
    line-height: 25px;
    font-weight: bold;
  }
  .follow{
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background-color: rgba(0,0,0,0.7);
    cursor:pointer;
    text-decoration: none;
  }
  .follow i{
    color: $orange;
    font-size: 1rem;
  }
  .electronic_symbol img{
    height: 80px;
    background-color: rgba(255,255,255,0.2);
    padding: 5px;
    border: 1px solid rgba(255,255,255,0.2);
  }
  .input-group{
    direction: ltr;
    background-color: rgba(255,255,255,0.4);
    border-radius: 2px;
    width: 350px;
  }
  .input-group > span > h5{
    color: #a6abc8;
    font-size: 0.7rem;
  }
  .form-control{
    border: 0px !important;
    font-size: 0.7rem;
    color: #616161;
    background-color: rgba(255,255,255,0.3);
    box-shadow: none !important;
    outline: none !important;
  }
  .input-group-text {
    border: 0px;
    background-color: transparent;
    cursor: pointer;
    font-size: 0.8rem;
    color: #fff;
    background-color: #413d77;
    text-decoration: none;
  }
  .input-group-text > img{
    width: 13px;
  }
  .footer_end{
    background-color: #d6d6d6
  }
  .footer_end p{
    color: #6f6f6f;
    font-weight: bold;
  }
</style>
