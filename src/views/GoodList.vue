<template>
  <div class="">

      <NavHeader></NavHeader>
      <!-- 头部 -->
        <!-- 
      <div class="header">
          <div class="header-left">
              
              <img class="header-nav-img" src="/static/img/logo2.gif" alt="">
              
          </div>
          <div class="header-right">
              <span>我的账户</span>
          </div>
      </div> -->

        <!-- con面包 -->

        <!-- <div class="nav-breadcrumb-wrap">
        <div class="container">
            <nav class="nav-breadcrumb">
            <a href="/">Home</a>
            <span>Goods</span>
            </nav>
        </div>
        </div> -->

        <NavBread>
            <span slot="bread">good</span>
            <span slot="B">测试一下</span>
        </NavBread>

        <div class="accessory-result-page accessory-page">
        <div class="container">
            <div class="filter-nav">
            <span class="sortby">Sort by:</span>
            <a href="javascript:void(0)" class="default cur">Default</a>
            <a href="javascript:void(0)" class="price">Price <svg class="icon icon-arrow-short"><use xlink:href="#icon-arrow-short"></use></svg></a>
            <a href="javascript:void(0)" class="filterby stopPop" @click="showFilterPop">Filter by</a>
            </div>
            <div class="accessory-result">
            
            <div class="filter stopPop" id="filter" v-bind:class="{'filterby-show':filterBy}">
                <dl class="filter-price">
                <dt>Price:</dt>
                <dd><a href="javascript:void(0)" v-bind:class="{'cur':priceChecked=='all'}" @click="priceChecked='all'">All</a></dd>
                <!-- 选中第一项然后下次点击就会显示第二项 -->
                <dd v-for="(price,index) in priceFilter" :key="price">
                    <a href="javascript:void(0)"  @click="setPriceFilter(index)" v-bind:class="{'cur':priceChecked==index}" >{{price.startPrice}}-{{price.endPrice}}</a>
                </dd>
                </dl>
            </div>

            
            <div class="accessory-list-wrap">
                <div class="accessory-list col-4">
                <ul>
                    <li>
                    <div class="pic">
                        <a href="#"><img src="/static/img/1.jpg" alt=""></a>
                    </div>
                    <div class="main">
                        <div class="name">XX</div>
                        <div class="price">XX</div>
                        <div class="btn-area">
                        <a href="javascript:;" class="btn btn--m">加入购物车</a>
                        </div>
                    </div>
                    </li>
                </ul>
                </div>
            </div>
            </div>
        </div>
        </div>

        <div class="md-overlay" v-show="overLayFlag" @click="closePop"></div>

        <NavFoorer></NavFoorer>
        
  </div>
</template>

<script>
import "./../assets/css/base.css"
import "./../assets/css/product.css"
import NavHeader from "@/components/NavHeader.vue"
import NavFoorer from "@/components/NavFooter.vue" 
import NavBread from "@/components/NavBread.vue"
export default {
  name: '',
  data() { 
    return {
        GoodList:[],
        priceFilter:[
            {
                startPrice:'0.00',
                endPrice:'500.00'
            },
            {
                startPrice:'500.00',
                endPrice:'1000.00'
            },
            {
                startPrice:'1000.00',
                endPrice:'2000.00'
            },
        ],
        priceChecked:"all",
        filterBy:false,
        overLayFlag:false
    }
  },
  props: {

  },
  components:{
      NavHeader,
      NavFoorer,
      NavBread

  },
  mounted() {

  },
  methods:{
      showFilterPop(){
          //价格的弹框
          this.filterBy=true,
        this.overLayFlag=true
      },
      setPriceFilter(index){
          this.priceChecked = index;
          this.closePop();
      },
      closePop(){
           this.filterBy=false,
        this.overLayFlag=false
      }
  },
watch:{

},
 }
</script>

<style>

.header{
    height: 80px;
}
  .header-nav-img{
      width: 150px;
      height: 50px;
      margin: 20px 0 20px 170px;
      float: left;
  }
  .header-right span{
      float: right;
      margin-top: 40px;
  }
</style>