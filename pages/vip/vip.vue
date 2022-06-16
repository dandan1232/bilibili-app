<template>
	<view>
		<!-- 导航栏 -->
		<uni-nav-bar fixed="false">
			<view slot="left" class="left-item">
				会员购
			</view>
			<view slot="mod" class="title-item">
				官方直营·正品保证
			</view>
			<view slot="right">
				<i class="iconfont icon-zhuangxiang right-icon" style="margin-left:-60px;"></i>
				<i class="iconfont icon-gouwuche right-icon" style="margin-left:10px;font-weight:bold;"></i>
				<i class="iconfont icon-geren right-icon" style="margin-left:10px;font-weight:bold;"></i>
			</view>
		</uni-nav-bar>
		<!-- 搜索框 -->
		<view class="input" @click="gotoSearch">
			<text class="iconfont icon-wddl" style="color: #d1d1d1; margin-left: 40%;" />
			<text style="color: #d1d1d1; margin-left: 3%;">魔力赏</text>
			<text class="iconfont icon-paizhao" style="color: #d1d1d1; margin-left: 30%;" />
		</view>
		<!-- 展示图片 -->
		<view class="image-view1">
			<view>
				<image class="img-small" src="../../static/smallcard/Garage Kit.png">
					<h2 class="reduce">手办</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/periphery.png">
					<h2 class="reduce">周边</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/movie.png">
					<h2 class="reduce">展演电影</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/book.png">
					<h2 class="reduce">图书漫画</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/games.png">
					<h2 class="reduce">游戏相关</h2>
				</image>
			</view>
		</view>
		<view class="image-view2">
			<view>
				<image class="img-small" src="../../static/smallcard/skirt.png">
					<h2 class="reduce">服饰鞋包</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/teacher.png">
					<h2 class="reduce">阴阳师</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/singer.png">
					<h2 class="reduce">虚拟歌手</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/fate.png">
					<h2 class="reduce">Fate</h2>
				</image>
			</view>
			<view>
				<image class="img-small" src="../../static/smallcard/all.png">
					<h2 class="reduce">全部分类</h2>
				</image>
			</view>
		</view>
		<view class="swiper-box">
			<!-- 轮播图 -->
			<swiper  class="swiper" :autoplay="true" :interval="2000" 
					:duration="500" :circular="true" indicator-dots="true"
					indicator-active-color="red" indicator-color="white" >
				<swiper-item>
					<image class="img-swiper" src="../../static/swiper-photos/01.jpg"></image>
				</swiper-item>
				<swiper-item>
					<image class="img-swiper" src="../../static/swiper-photos/02.jpg"></image>
				</swiper-item>
				<swiper-item>
					<image class="img-swiper" src="../../static/swiper-photos/03.jpg"></image>
				</swiper-item>
				<swiper-item>
					<image class="img-swiper" src="../../static/swiper-photos/04.jpg"></image>
				</swiper-item>
				<swiper-item>
					<image class="img-swiper" src="../../static/swiper-photos/05.jpg"></image>
				</swiper-item>
				<swiper-item>
					<image class="img-swiper" src="../../static/swiper-photos/06.jpg"></image>
				</swiper-item>
			</swiper>
			<!-- right-box box -->
			<view class="right-box">
				<view style="font-size: 32rpx; font-weight: 600; margin: 12rpx;">魔力赏</view>
				<view style="color: #8A6DE9; margin-top: -50rpx; margin-left: 120rpx;">
					免费试玩赢奖励
				</view>
				<image src="../../static/card/07.png" style="width: 100rpx; height: 160rpx; margin-left: 50rpx;"></image>
				<image src="../../static/card/08.png" style="width: 100rpx; height: 160rpx; margin-left: 40rpx;"></image>
			</view>
		</view>
		<!-- button -->
		<view class="button-item">
			<button size="mini" @click="gotoTodayNews">今日上新
				<i class="iconfont icon-shandian"></i>
			</button>
			<button size="mini" @click="gotoFirstLook">抢先看
				<i class="iconfont icon-mulu"></i>
			</button>
			<button size="mini" @click="gotoRankingList">排行榜
				<i class="iconfont icon-paihangbang"></i>
			</button>
			<button size="mini" @click="gotoIpParadise">IP乐园
				<i class="iconfont icon-icon-test"></i>
			</button>
		</view>
		<!-- 卡片 -->
		<!-- 瀑布流布局列表 -->
		<view class="Index">
			<!-- 瀑布流布局列表 -->
			<view class="pubuBox">
				<view class="pubuItem">
					<view class="item-masonry" v-for="(vip, index) in Vips" :key="index">
						<image :src="vip.cover" mode="widthFix"></image>
						<view class="listtitle"> <!-- 这是没有高度的父盒子（下半部分） -->
							<view class="list-name">{{ vip.project_name }}</view>
							<view class="list-flag">
								{{vip.sale_flag}}
							</view>
							<view class="list-price">
								￥{{ vip.price_high }}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 底线 -->
		<image src="../../static/card/loading.png" style="margin-top: -80%; margin-left: 5%;"></image>
	</view>
</template>

<script>
	import uniNavBar from '../../components/uni-ui/uni-nav-bar/uni-nav-bar.vue'
	import uniCard from '@/components/uni-ui/uni-card/uni-card.vue'
	import uniList from '../../components/uni-ui/uni-list/uni-list.vue'
	import uniListItem from '../../components/uni-ui/uni-list-item/uni-list-item.vue'
	export default {
	    components: {
			uniNavBar, 
			uniCard, 
			uniList, 
			uniListItem,
			
		},
		data() {
			return {
				keyword: '',
				Vips: [],
			};
		},
		onShow() {},
		onLoad() {
			uni.request({
				url:'https://show.bilibili.com/api/ticket/project/listV3?version=133&page=1&pagesize=20&platform=web&area=-1&p_type=全部类型&style=1&buvid=9E1A8BC2-CC7E-45EA-9C9B-BCCCCAE10112184999infoc&mid=480185780' + this.page,
				success: (res) => {
					// console.log(res);
					this.Vips = res.data.data.result;
					for (let i = 0; i < this.Vips.length; i++) {
						this.Vips[i].cover = 'https:'+this.Vips[i].cover
						// console.log(this.Vips[i].cover);
					}
				}
			});
		},
		methods: {
			gotoSearch() {
				console.log("进入搜索页面")
				uni.navigateTo({
					url: '../search/search',
					success() {
						console.log("#####################")
					},
					fail(err) {
						console.log(err)
						console.log("错误****************************")
					}
				});
			},
			gotoTodayNews() {
				uni.navigateTo({
				    url:'./today-news.vue',
				})
			},
			gotoFirstLook() {
				uni.navigateTo({
				    url:'./first-look.vue',
				})
			},
			gotoRankingList() {
				uni.navigateTo({
				    url:'./ranking-list.vue',
				})
			},
			gotoIpParadise() {
				uni.navigateTo({
				    url:'./ip-paradise.vue',
				})
			},
		},
		
	}
</script>

<style  scoped="scoped">
.left-item {
	font-size: 38rpx;
	font-weight: 600;
	margin-left: 5%;
}
.title-item {
	color: #BDBDBD;
	font-size: 30rpx;
	margin-top: 1%;
}
.right-icon {
	font-size: 38rpx;
	color: #BDBDBD;
}
.input {
	margin-top: 15%;
	height: 30px;
	margin-bottom: 10px;
	margin-left: 5%;
	width: 90%;
	border-radius:30px;
	background-color: #f6f6f6;
}
.image-view1 {
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: space-around;
	align-items: flex-start;
}
.image-view2 {
	margin-top: 30rpx;
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: space-around;
	align-items: flex-start;
}
.img-small {
	height: 100rpx;
	width: 100rpx;
}
.reduce {
	font-size: 24rpx;
	align-items: center;
	display: flex;
	flex-direction: column;
}
.swiper-box{
	 border-radius:30rpx;
	 display: flex;
}
.swiper {
	margin-left: 15rpx;
	margin-top: 40rpx;
 	height: 250rpx;
	width: 340rpx;
}
.img-swiper{  
    width: 340rpx;  
    height: 140px;
	border-radius:40rpx
} 
.right-box {
	margin-left: 35rpx;
	margin-top: 40rpx;
	height: 250rpx;
	width: 340rpx;
	background-image: linear-gradient(Lavender,white);
	border-radius:40rpx
}
.button-item {
	margin-top: 5%;
	display: flex;
	flex-wrap: wrap;
}
/deep/button{
	font-size: 12px !important;
}
/* 去掉uniapp中button自带的边框 */
/deep/button::after {
	border: none
}
.icon-shandian {
	color: #FFEE58;
}
.icon-mulu {
	color: #81D4FA;
}
.icon-paihangbang {
	color: #FF80AB;
}
.icon-icon-test {
	color: #9CCC65;
}
page {
	background-color: #FFFFFF;
	height: 100%;
}
.pubuBox {
	padding: 20rpx;
}
.pubuItem {
	column-count: 2;
	column-gap: 20rpx;
}
.item-masonry {
	box-sizing: border-box;
	border-radius: 15rpx;
	overflow: hidden;
	background-color: #fff;
	break-inside: avoid;
	/*避免在元素内部插入分页符*/
	box-sizing: border-box;
	margin-bottom: 15rpx;
	box-shadow: 0px 0px 28rpx 1rpx rgba(213, 213, 213, 0.1);
}
.item-masonry image {
	width: 100%;
}
.listtitle {
	padding-left: 22rpx;
	font-size: 24rpx;
	/* padding-bottom: 22rpx; */
}
.list-name {
	font-size: 30rpx;
}
.list-flag {
	color: #FF80AB;
	font-size: 24rpx;
	font-weight: bold;
}
.list-price {
	font-size: 28rpx;
	color: #FF80AB;
}
.Index {
	width: 100%;
	height: 100%;
}
</style>
