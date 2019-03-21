<template>
  <div class="wrap">
    <header>
      面试信息
    </header>
    
      <ul class="main">
        <li>
          <p>公司名称</p>
          <input type="text" v-model="current.company" placeholder="请输入公司名称">
        </li>
        <li>
           <p>公司电话</p>
           <input type="text" v-model="current.phone" placeholder="请输入公司电话" maxlength="11">
        </li>
        <li>
           <p>面试时间</p>
           <input type="text"  placeholder="请输入面试时间">
        </li>
        <li>
           <p>面试地点</p>
           <input  @click="search" type="text" v-model="current.address.address" placeholder="请输入面试地点">
        </li>
      </ul>
   
    <p class="p">备注信息</p>
    <textarea type="text" v-model="current.description" placeholder="备注信息(可选，100个字以内)"/>
    <button :class="btnEnable?'':'disable'">确认</button>
    
  </div>
</template>

<script>

// import {getLocation, getAuth} from '@/utils/index.js'
import {mapState, mapMutations} from 'vuex'
// const moment=require('moment');
// console.log(moment)
export default {
  data() {
      return {
       
      };
    },
  computed: {
    ...mapState({
      current: state=>state.interview.current
    }),
    btnEnable(){
     // console.log(this.current.company)获取公司名字
      // if(!this.current.company){
      //   return false;
      // }
      // if(!/^1([38]\d|5[0-35-9]|7[3678])\d{8}$/.test(this.current.phone)||/0\d{2}-\d{7,8}/.test(this.current.phone)){
      //   return false;
      // }
      // if(!this.current.address){
      //   return false;
      // }
      // return true;
    }
  },

  methods: {
    ...mapMutations({
     
    }),
    search(){
      wx.navigateTo({
        url:"/pages/search/main"
      })
    }
  }
}
</script>






<style lang="scss" scoped>
p{
    width:180rpx;
    text-align: center;
    display: flex;
    height: 100%;
    margin-right: 10rpx;
   }
 button{
   height:120rpx;
   width:96%;
   line-height:120rpx;
   margin-bottom: 30rpx;
   background: skyblue;
   position: absolute;
   bottom: 50rpx;
   left: 0;
   margin: 0 15rpx;
}
.wrap{
   width: 100%;
   height:100%;
    background: #eeeeee;
}
header{
  width: 100%;
  height:120rpx;
  background: #fff;
  line-height: 120rpx;
  font-weight: bold;
  padding: 0 20rpx;
  box-sizing: border-box;
   border-top:2rpx solid #dddddd; 
}

.main{
  display: flex;
  background: #cccccc;
  flex-direction: column;
  li{
    width: 100%;
    height: 100rpx;
    line-height: 100rpx;
    padding: 0 20rpx;
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    border-top:2rpx dashed #dddddd; 
    background: #ffffff;
  p{
      width:180rpx;
      text-align: center;
      display: flex;
      height: 100%;
      margin-right: 10rpx;
    }
   input{
     flex: 1;
     height: 100%;
     overflow: hidden;
     white-space: nowrap;
     text-overflow: ellipsis;
   }
  }
  
  
}
textarea{
    font-size: 30rpx;
  background: #eee;
  color: #333;
  width: 690rpx;
  height: 200rpx;
  margin: 0 auto;
  box-sizing: border-box;
  padding: 10rpx;
  border: 3rpx solid #c0c0c0;
  border-radius: 5rpx;
  }
.p{
  width:180rpx;
  text-align: center;
  display: flex;
  height:100rpx;
  line-height: 100rpx;
  padding: 0 10rpx;
  box-sizing: border-box;
  }

.btnEnable{
  background: #333;
}
</style>
