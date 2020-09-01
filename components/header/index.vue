<template>
  <div class="bg-gray position-relative ">
    <div class="pattern position-absolute" :style="{ backgroundImage: `url(${backgroundUrl})` }"></div>
    <div class="pattern2 position-absolute" style="background-color: #47494e"></div>
    <div class="position-relative" style="z-index: 2">
      <!--  start of contact information   -->
      <div class="top_header d-flex flex-column flex-md-row align-items-center justify-content-between px-0 px-md-5 py-3">
        <div class="col-12 col-md-4 d-flex justify-content-center justify-content-md-start follow mb-3 mb-md-0 p-0">
          <a v-for="item in websiteInfo.socials" :href="item.src" >
            <i :class="`fa fa-${item.icon}`"></i>
          </a>
        </div>
        <div class="col-12 col-md-4 d-none d-md-block justify-content-center p-0">
          <SearchBox />
        </div>
        <div class="col-12 col-md-4 d-flex justify-content-center justify-content-md-end p-0 info">
          <span class="ml-3">{{websiteInfo.email}}<i class="fa fa-envelope mr-2"></i></span>
          <span class="">{{websiteInfo.phone}}<i class="fa fa-phone mr-2"></i></span>
        </div>
    </div>
      <!--  end of contact information   -->

      <!--  start of navbar   -->
      <div class="middle_header mx-0 mx-md-5">
        <b-navbar toggleable="lg" type="light" variant="white" class="p-0">
          <b-navbar-brand href="#" class="logo_container">
            <img :src="require('@/assets/image/' + websiteInfo.logoImg)">
            <a class="navbar-brand" href="#">{{websiteInfo.name}}</a>
          </b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav class="mr-0 mr-md-5 px-4 pl-md-0 pr-md-5">
              <div v-for="link in navbarLinks">
                <b-nav-item  v-if="!link.subMenu" :to="link.href">
                  <div class="d-flex">
<!--                  <i class="fa fa-home d-block d-md-none ml-2"></i>-->
                  <span> {{link.name}}</span>
                  </div>
                </b-nav-item>
                <b-nav-item-dropdown :text="link.name" v-else right class="menu">
                    <b-dropdown-item  v-for="subLink in link.subMenu" :to="`${link.href}/${subLink.name}`">{{subLink.name}}</b-dropdown-item>
                </b-nav-item-dropdown>
              </div>
            </b-navbar-nav>

            <!--  NAVBAR BUTTONS  -->
            <div class="mx-4 mr-md-auto">
              <div v-if="token">
                <b-nav-item-dropdown text="نام و نام خانوادگی" class="menu" left>
                  <b-dropdown-item href="#">محصولات خریداری شده</b-dropdown-item>
                  <b-dropdown-item href="#">فاکتور خرید</b-dropdown-item>
                </b-nav-item-dropdown>
              </div>
              <div v-else class="header_button d-flex justify-content-around bg-orange">
                <b-nav-item
                  href="#" v-b-modal.modal-no-backdrop class="login position-relative">ورود</b-nav-item>
                <b-modal id="modal-no-backdrop"  hide-backdrop content-class="shadow"
                         header-text-variant="light" title="ورود به سیتم">
                  <b-input-group>
                    <template v-slot:prepend>
                      <div class="prependIcon"><i class="fa fa-envelope"></i></div>
                    </template>
                    <b-form-input  size="sm" placeholder="پست الکترونیکی"></b-form-input>
                  </b-input-group>
                  <b-input-group class="mt-3">
                    <template v-slot:prepend>
                      <div class="prependIcon"><i class="fa fa-lock"></i></div>
                    </template>
                    <b-form-input size="sm" placeholder="رمز عبور"></b-form-input>
                  </b-input-group>
                  <template v-slot:modal-footer="{ ok }">
                    <!-- Emulate built in modal footer ok and cancel button actions -->
                    <b-button size="sm" variant="success" @click="ok()">
                      ورود
                    </b-button>
                  </template>
                </b-modal>
              </div>
            </div>
            <!--  END OF NAVBAR BUTTONS  -->
          </b-collapse>

          <div class="d-block d-md-none w-100 mx-4 my-3">
            <SearchBox />
          </div>

        </b-navbar>
      </div>
      <!--   end of navbar   -->
    </div>
  </div>
</template>

<script>
    import backgroundUrl from '@/assets/image/pattern.png'
    import SearchBox from './searchBox'
    export default {
        name: "index",
        data() {
          return {
            backgroundUrl,
            token:false,
            navbarLinks:[
              {
                name:'صفحه اصلی',
                href:'/',
              },
              {
                name:'محصولات',
                href:'/products/category',
                subMenu:[
                  {
                    name:'کولر',
                    href:''
                  },
                  {
                    name:'بخاری',
                    href:''
                  },
                  {
                    name:'شوفاژ',
                    href:''
                  },
                ]
              },
              {
                name:'خدمات',
                href:'/services/all'
              },
              {
                name:'نمونه کارها',
                href:'/portfolio'
              },
              {
                name:'درباره ما',
                href:'/aboutUs',
              },
              {
                name:'تماس با ما',
                href:'#footer',
              },
            ],
            websiteInfo:{
              name:'نام وب سایت',
              logoImg:'logo.png',
              email:'info@mysite.com',
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
       },
      components:{
          SearchBox,
      }
    }
</script>

<style lang="scss" scoped>
  @media (max-width: 991px) {
    .top_header form{
      width: 90% !important;
    }
    .middle_header{
      background-color: $orange;
      padding: 5px 0;
    }
    .nav-item{
      padding: 5px;
      border-bottom: 1px solid $orange;
    }
    .nav-item i{
      font-size: 1rem;
    }
  }
  @media (min-width: 992px) {
    .logo_container::before {
      right: 100px;
      width: 200px;
      transform: skew(-30deg);
    }

    .logo_container::after, .logo_container::before {
      background-color: #fff;
      content: "";
      position: absolute;
      top: 0;
      height: 100%;
      z-index: -1;
    }
    #nav-collapse {
      height: 60px;
      background-color: $orange;
      border-top: 1px solid #fff;
      border-bottom: 1px solid #fff;
    }
    /*.header_button .login:after{*/
    /*  content: "";*/
    /*  height: 13px;*/
    /*  width: 1px;*/
    /*  background-color: rgba(255,255,255,0.3);*/
    /*  position: absolute;*/
    /*  top: 11px;*/
    /*  left: 0;*/
    /*}*/
  }

  .bg{
    /*<!--background:linear-gradient($darkGray,$lightGray);-->*/
    background-color: $darkGray;
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
  .pattern2{
    width: 100%;
    height: 93px;
  }
  .top_header .follow i{
    font-size: 0.8rem !important;
    cursor: pointer;
    border-right: 1px solid rgba(255,255,255,0.3);
    padding: 0 15px;
    color: rgba(255,255,255,0.8);
  }
  .top_header .follow i:hover{
    color: rgba(255,255,255,0.7);
  }
  .top_header .follow a:first-child i{
    border-right: none !important;
    padding-right: 0px !important;
  }
  .top_header .info span{
    color: rgba(255,255,255,0.8);
    font-size: 0.8rem;
  }
  .middle_header{
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
  }
  .logo_container {
    z-index: 9;
  }
  .logo_container img{
    width: 50px;
    height: auto;
  }
  .navbar-toggler{
    outline: none !important;
    border: none !important;
    margin-left: 10px;
    color: rgba(0,0,0,1) !important;
  }
  .navbar-toggler-icon{
    color: rgba(0,0,0,1) !important;
  }
  .navbar-brand{
    color: #877f77 !important;
    font-size: 1.5rem;
    font-weight: bold;
  }
  .navbar-brand > span{
    color: #ad9d6a !important;
  }
  .header_button a {
    color: #fff0e0 !important;
  }
  li{
    border-bottom: none;
    list-style-type: none;
  }
  .modal-footer .btn{
    background-color: $orange;
    border: none !important;
    padding: 5px 40px;
    border-radius: 2px;
    font-size: 0.9rem;
  }
  .prependIcon{
    font-size: 1rem;
    margin-left: 10px;
    color: rgba(0,0,0,0.5);
    display: flex;
    align-items: center;
  }
</style>
<style lang="scss">
  @media(min-width:992px ) {
    .navbar .nav-link, .header_button a {
      color: #fff0e0 !important;
      padding-left: 15px !important;
      font-size: 1rem;
      outline: none;
      box-shadow: none;
    }
    .dropdown-menu {
      text-align: right !important;
      margin: 0.6rem 0 0;
      border-radius: 0;
      padding: 0px;
      box-shadow: 0 2px 3px rgba(0, 0, 0, 0.2);
    }
    .dropdown-item{
      border-bottom: 1px solid #eeeeee;
    }
  }
  @media (max-width: 991px) {
    .nav-link{
      color: rgba(0,0,0,0.5) !important;
      text-align: right;
    }
    .dropdown-item{
      text-align: right;
      border-bottom: 1px solid #f5bba1;
    }
    .dropdown-menu{
      margin-right: 15px;
      border: none;
    }
    .dropdown-menu li:last-child .dropdown-item{
      border-bottom:none ;
    }
  }
  .navbar  .nav-link, .header_button a{
    font-size: 0.9rem;
    font-weight: bold;
  }
  .dropdown-item{
    color: rgba(0,0,0,0.7);
    font-size: 0.9rem;
    padding: 10px;
    padding-right: 15px;
  }
  .dropdown-toggle::after{
    margin-right: 0.745em;
  }
  .close{
    padding: 0px !important;
    margin: 0px !important;
  }
  .modal-title{
    font-size: 1rem !important;
  }
  .modal-content{
    margin-top:120px !important ;
  }
  .modal-content , .modal-header{
    border-radius: 1px !important;
  }
  .modal-body input{
    box-shadow: none !important;
    outline: none !important;
    border: none !important;
    border-bottom: 1px solid rgba(0,0,0,0.2) !important;
    border-radius: 0px !important;
  }
  .modal-footer{
    border-top: none !important;
  }
  .modal-header{
    padding:10px !important;
    background-color: $darkGray;
  }
  .modal-header button{
    outline: none !important;
    border: none !important;
  }
</style>
