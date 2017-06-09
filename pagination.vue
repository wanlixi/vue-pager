<!--
功能描述：分页组件
-->
<template>
  <div class="pagination">
  	<div class="pagesnum">
  	  <span>{{pageno}}</span>/{{totalpages}}
  	</div>
  	<div class="pagebtns">
  	  <a @click="lastpage">＜</a>
  	  <a @click="prepage">＞</a>
  	</div>
  </div>
</template>
<script type="text/babel">
export default {
  data () {
  	return {
      
  	}
  },
  props: {
  	pageno:{
      type:Number,
      default:1
    },
    totalpages:{
      type:Number,
      default:10
    }
  },
  methods: {
    lastpage(){
      if(this.pageno>1){
        this.pageno--
        this.$parent.getStock(this.pageno)
      }
    },
    prepage(){
      if(this.pageno<this.totalpages){
        this.pageno++
        this.$parent.getStock(this.pageno)
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
$color =#00e2f5
.pagination
  display flex
  padding 10px 0
  justify-content flex-end
  .pagesnum
    margin-right 10px
    color #666
    span
      color $color
  .pagebtns
    margin-right 30px
    display flex
    a
      display block
      width 40px
      height 24px
      margin-left 7px
      border 0
      font 20px/24px '微软雅黑'
      text-align center
      color #fff
      background url('~assets/img/index/nav-item-bg.jpg') no-repeat
      background-size 100% 100%
</style>