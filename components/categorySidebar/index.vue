<template>
    <div>
      <b-card no-body class="mb-2">
        <b-card-header header-tag="header" class="p-0" role="tab">
          <b-button block v-b-toggle="'accordion-'+attributeGroup.id" variant="white">{{attributeGroup.title}}</b-button>
        </b-card-header>
        <b-collapse :id="'accordion-'+attributeGroup.id" accordion="my-accordion" role="tabpanel">
          <b-card-body class="p-0">
            <b-card-text>
              <div class="border-bottom pb-3 my-3 mx-2">
                <form class="position-relative form-inline">
                  <input type="text" placeholder="جستجو کنید..." v-model="filterText">
                  <i class="fa fa-search position-absolute"></i>
                </form>
              </div>
              <div class="itemContainer px-4">
                <b-form-checkbox-group
                  v-model="selected"
                  :options="filter"
                  class="mb-3"
                  value-field="item"
                  text-field="name"
                  disabled-field="notEnabled"
                  stacked
                ></b-form-checkbox-group>
              </div>
            </b-card-text>
          </b-card-body>
        </b-collapse>
      </b-card>
<!--      <div v-if="attributeGroup.type='checkbox'">-->
<!--       -->
<!--      </div>-->

<!--      <div v-if="attributeGroup.type='range'">-->
<!--        <label for="range-1">Example range with min and max</label>-->
<!--        <b-form-input id="range-1" v-model="value" type="range" min="0" max="5"></b-form-input>-->
<!--      </div>-->

<!--      <div v-if="attributeGroup.type='switch'">-->
<!--        <b-form-checkbox v-model="checked" name="check-button" switch>-->
<!--          Switch Checkbox <b>(Checked: {{ checked }})</b>-->
<!--        </b-form-checkbox>-->
<!--      </div>-->

    </div>
</template>

<script>
  export default {
    name: "index",
    props:['attributeGroup'],
    data() {
      return {
        selected: [],
        options: [],
        filterText:'',
        items:[],
      }
    },
    computed:{
      filter(){
        this.items = this.attributeGroup.attributeValues;
        console.log(this.items);
        return this.items.filter((element)=>{
          return element.match(this.filterText)
        })
      }
    }
  }
</script>

<style lang="scss" scoped>
  .card-header{
    background-color: transparent;
  }
  .card{
    box-shadow: 0 0 3px rgba(0,0,0,0.1);
  }
  .btn{
    color: $title;
    text-align: right;
    font-size: 0.8rem;
    font-weight: bold;
    border-radius: 0px !important;
    padding: 10px;
    outline: 0 !important;
    box-shadow: none !important;
    border: none !important;
  }
  .btn:focus{
    background-color: rgba(0,0,0,0.1);
  }
  .btn:focus{
    outline: none !important;
    border: none !important;
    box-shadow: none !important;
  }
  .sidebar h4{
    font-size: 0.9rem;
    border-bottom: 1px solid #e0e0e0 !important;
    color: rgb(121, 121, 121);
  }
  .sidebar h5{
    font-size: 0.9rem;
    color:rgb(112, 112, 112)
  }
  .sidebar ul li{
    list-style-type: none;
    text-align: right;
  }
  .sidebar ul li a{
    text-decoration: none;
    color: rgb(144, 144, 144);
    font-size: 0.8rem;
  }
  .form-inline{
    background-color: transparent;
    width: 100%;
    border: 1px solid rgba(0,0,0,0.3);
  }
  .form-inline > input{
    background-color: transparent;
    min-width: 100% !important;
    border: none !important;
    outline: none !important;
    color: $title;
    padding:5px 10px;
    padding-left: 32px;
  }
  .form-inline > input::placeholder{
    color: $title;
  }
  .form-inline > i{
    position: absolute;
    top: 7px;
    left: 9px;
    cursor: pointer;
    color: rgba(0,0,0,0.5);
  }
  .itemContainer{
    max-height: 200px;
    overflow-y: scroll;
  }
</style>
<style>
  .custom-control-label::before{
    right: -1.5rem !important;
  }
  .custom-control{
    text-align: right !important;
    padding-right: 1.5rem !important;
    margin:5px 0;
  }
  .custom-control-input{
    right: 0 !important;
  }
</style>
