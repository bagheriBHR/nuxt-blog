<template>
  <div class="sidebar d-flex flex-column align-items-start">
    <div class="d-flex flex-column align-item-start w-100">
      <b-card no-body class="mb-2" v-for="item in attributeGroups" :key="item.title">
        <b-card-header header-tag="header" class="p-0" role="tab">
          <b-button block v-b-toggle="'accordion-'+item.title" variant="white">{{item.title}}</b-button>
        </b-card-header>
        <b-collapse :id="'accordion-'+item.title" accordion="my-accordion" role="tabpanel">
          <b-card-body>
            <b-card-text>
              <b-form-checkbox-group
                v-model="selected"
                :options="item.attributeValues"
                class="mb-3"
                value-field="item"
                text-field="name"
                disabled-field="notEnabled"
                stacked
              ></b-form-checkbox-group>
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
  </div>
</template>

<script>
  export default {
    name: "index",
    props:['attributeGroups'],
    data() {
      return {
        selected: [],
        options: [

        ]
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
