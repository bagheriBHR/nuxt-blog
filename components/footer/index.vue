<template>
    <div>
      <div class="bg-footer d-flex flex-column">
        <div class="top d-flex justify-content-center p-3">
          <div class="col-12 col-md-8 d-flex">
            <sale-garantee  imageName="money.png" title="تضمین بهترین قیمت"/>
            <sale-garantee  imageName="certificate.png" title="ضمانت اصالت کالا"/>
            <sale-garantee  imageName="maintenance.png" title="خدمات پس از فروش"/>
            <sale-garantee  imageName="calculator.png" title="خرید اقساطی"/>
          </div>
        </div>

        <div class="d-flex flex-column flex-md-row">
          <div class="col-12 col-md-4 d-flex flex-column flex-md-row mt-4">
            <div class="footer_part col-12 col-md-6 d-flex flex-column">
              <h2 class="part_title">اطلاعات</h2>
              <ul class="p-0">
                <Li title="مقالات"/>
                <Li title="بلاگ"/>
                <Li title="تماس با ما"/>
                <Li title="خدمات پس از فروش"/>
                <Li title="سوالات متداول"/>
              </ul>
            </div>
            <div class="footer_part col-12 col-md-6 d-flex flex-column">
              <h2 class="part_title">جدیدترین محصولات</h2>
              <ul class="p-0">
                <Li title="محصول 1"/>
                <Li title="محصول 2"/>
                <Li title="محصول 3"/>
                <Li title="محصول 4"/>
                <Li title="محصول 5"/>
              </ul>
            </div>
          </div>
          <div class="contact_part col-12 col-md-4 d-flex align-items-center position-relative">
<!--            <div class="pattern position-absolute" :style="{ backgroundImage: `url(${backgroundUrl})` }"></div>-->
            <div class="d-flex flex-column p-3">
              <div class="d-flex">
                <i class="fa fa-map-marker ml-3"></i>
                <p class="text-justify">لورم ایپسوم یا طرح‌نما (به انگلیسی: Lorem ipsum) به متنی آزمایشی و بی‌معنی در صنعت چاپ، صفحه‌آرایی و طراحی گرافیک</p>
              </div>
              <div class="d-flex">
                <i class="fa fa-phone ml-3"></i>
                <p class="text-justify">تلفن : 09139912691</p>
              </div>
              <div class="d-flex">
                <i class="fa fa-envelope ml-3"></i>
                <p class="text-justify mb-0">ایمیل : info@mysite.com</p>
              </div>
              <div class="d-flex align-items-center justify-content-center mt-4">
                <a class="follow d-flex align-items-center justify-content-center mx-2"><i class="fa fa-whatsapp"></i></a>
                <a class="follow d-flex align-items-center justify-content-center mx-2"><i class="fa fa-telegram"></i></a>
                <a class="follow d-flex align-items-center justify-content-center mx-2"><i class="fa fa-instagram"></i></a>
                <a class="follow d-flex align-items-center justify-content-center mx-2"><i class="fa fa-facebook"></i></a>
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
    import SaleGarantee from '@/components/footer/saleGarantee'
    import Li from '@/components/footer/li'
    import backgroundUrl from '@/assets/image/pattern.png'
    import { BIcon } from 'bootstrap-vue'
    export default {
        name: "index",
        components:{
          SaleGarantee,
          Li,
      },
      data() {
        return { backgroundUrl }
      }
    }
</script>

<style lang="scss" scoped>
  .top{
    background-color: #d6d6d6;
    box-shadow: 0 1px 2px rgba(0,0,0,0.1);
  }
  .part_title{
    font-size: 0.9rem !important;
    color: rgba(0,0,0,0.6);
    text-align: right;
    margin-bottom: 20px;
    padding-bottom: 10px;
    font-weight: bold;
    border-bottom: 1px solid rgba(0,0,0,0.1);
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
