<template>
  <view>
  <uni-nav-bar class="nav">
    <view slot="left" @click="back">
      <text class="iconfont icon-right-angle"  />    
    </view>
  <view slot="mod">
     <text>我推荐的视频</text>  
  </view>
   
  </uni-nav-bar>
    <view>
      <view class="card1">
         <!-- 图文卡片模式 -->
         <uni-card
           title="90.9万"
           mode="style"
           :is-shadow="true"
           thumbnail="/static/zoom/4.webp"
           extra=""
         >
         【对阿网】英语四级考试全套课程
         </uni-card>
         <uni-card
           title="82.4万"
           mode="style"
           :is-shadow="true"
           thumbnail="/static/zoom/6.webp"  
         >
         【纯干货】10天过英语四级的复习方法
         </uni-card>
       <view class="card1">
          <!-- 图文卡片模式 -->
          <uni-card
            title="90.9万"
            mode="style"
            :is-shadow="true"
            thumbnail="/static/zoom/4.webp"
            extra=""
          >
          【对阿网】英语四级考试全套课程
          </uni-card>
          <uni-card
            title="82.4万"
            mode="style"
            :is-shadow="true"
            thumbnail="/static/zoom/6.webp"  
          >
          【纯干货】10天过英语四级的复习方法
          </uni-card>
       </view>  <view class="card1">
       <!-- 图文卡片模式 -->
       <uni-card
         title="90.9万"
         mode="style"
         :is-shadow="true"
         thumbnail="/static/zoom/4.webp"
         extra=""
       >
       【对阿网】英语四级考试全套课程
       </uni-card>
       <uni-card
         title="82.4万"
         mode="style"
         :is-shadow="true"
         thumbnail="/static/zoom/6.webp"  
       >
       【纯干货】10天过英语四级的复习方法
       </uni-card>
    </view>  
      </view>  
    </view>
 </view>
</template>

<script>
  import uniNavBar from "../../components/uni-ui/uni-nav-bar/uni-nav-bar.vue"
  export default {
    components:{
      uniNavBar
    },
    data() {
      return {
        
      }
    },
    methods: {
      back(){
        uni.navigateTo({
          url:'../zoom/zoom'
        })
      },
    }
  }
</script>

<style>
.nav {
  background: transparent;
  position: sticky;
  top: 44px;
  top: 0;
  z-index: 3;
}

</style>
