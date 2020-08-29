<template>
  <form class="position-relative form-inline" :class="{active : isActive}">
    <input
      type="text"
      placeholder="کالا مورد نظر خود را وارد کنید..."
      @focus="isActive=true"
      @blur="isActive=false"
      v-model="searchText"
      maxlength="50"
    >
    <i class="fa fa-close" v-if="searchText" @click="searchText=''"></i>
    <i class="fa fa-search"></i>
  </form>
</template>

<script>
    export default {
        name: "index",
      data(){
          return{
            isActive:false,
            searchText:''
          }
      }
    }
</script>

<style scoped>
  .form-inline{
    background-color: #636363;
    width: 100%;
    box-shadow: 0 0 3px rgba(0,0,0,0.1);
  }
  .form-inline > input{
    background-color: transparent;
    min-width: 100% !important;
    border: none !important;
    outline: none !important;
    color: #fff;
    padding:5px 10px;
    padding-left: 47px;
  }
  .form-inline > input::placeholder{
    color: rgba(255,255,255,0.5);
  }
  .form-inline > i{
    position: absolute;
    top: 7px;
    left: 9px;
    cursor: pointer;
    color: rgba(255,255,255,0.7);
  }
  .fa-close{
    left: 30px !important;
    font-weight: normal;
  }

  @media (min-width: 992px) {
    .active{
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
      background-color: #6f6f6f;
    }
  }
  @media (max-width: 991px) {
    .active{
      box-shadow: 0 0 5px rgba(0,0,0,0.2);
      background-color: #6f6f6f;
    }
  }

</style>
