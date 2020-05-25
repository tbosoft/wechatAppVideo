<style scoped lang='scss'>
	
	.storeListVideo image {
	  width: 100%;
	  height: 100%;
	  position: absolute;
	  bottom: 0;
	  right: 0;
	}

	.card-def {
		.content {
			position: relative;

			.pic {
				width: 100%;
				height: 200px;
			}

			.tip {
				position: absolute;
				right: 5px;
				bottom: 10px;
				padding: 2px 3px;
				background-color: #a2a2b6;
				background-color: rgba(162, 162, 182, .5);
				color: #fff;
				font-size: 10px;
				line-height: 1;
			}
		}


		.name {
			margin-top: 6px;
			color: #000028;
			font-size: 14px;
			line-height: 20px;
			white-space: nowrap;
			text-overflow: ellipsis;
			overflow: hidden
		}

		.desc {
			

			position: absolute;
			top: 3%;
			left: 3%;
			color: #ffffff;
			font-size: 14px;
			width: 95%;

		}
		.viewButtom {
		  height: 76rpx;
		  width: 94.22%;
		  margin: 0 3.47% 0 2.31%;
		  position: relative;
		  display: flex;
		  justify-content: space-between;
		  align-items: center;
		  box-sizing: border-box;
		}
		.viewItem{
			display: flex;
			justify-content: space-between;
			align-items: center;
		}
		.typeIcon {
		  width: 52rpx;
		  height: 44rpx;
		  /* margin-top: 8rpx; */
		}
		.wechatIcon {
		  width: 40rpx;
		  height: 40rpx;
		  margin-right: 5upx;
		  /* margin-top: 8rpx; */
		}
		.watchNum{
			color: #000028;
			font-size: 14px;
			line-height: 20px;
			white-space: nowrap;
			text-overflow: ellipsis;
			overflow: hidden;
			
		}
		.shareCommand{
			display: flex;
			justify-content: flex-end;
			align-items: center;
			box-sizing: border-box;
			border: 1px solid #999999;
			border-radius: 9px 9px 9px 9px;
			padding-left: 15upx;
			padding-right: 15upx;
			padding-top: 6upx;
			padding-bottom: 6upx;

			
			
		}
		.shareNum{
			color: #000028;
			font-size: 12px;
			line-height: 20px;
			white-space: nowrap;
			text-overflow: ellipsis;
			overflow: hidden;
			
		}
		
		

	}

	.card-line {
		display: flex;

		.left {

			position: relative;
			width: 100px;
			margin-right: 10px;

			.pic {
				width: 100px;
				height: 120px;
			}

			.tip {
				position: absolute;
				right: 5px;
				bottom: 10px;
				padding: 2px 3px;
				background-color: #a2a2b6;
				background-color: rgba(162, 162, 182, .5);
				color: #fff;
				font-size: 10px;
				line-height: 1;
			}
		}
		

		.right {
			flex: 1;
			display: flex;
			flex-direction: column;

			.name {
				margin-top: 6px;
				color: #000028;
				font-size: 14px;
				line-height: 20px;
				
				overflow: hidden;
				text-overflow: ellipsis;
				display: -webkit-box;
				-webkit-line-clamp: 1;
				 -webkit-box-orient: vertical;
			}
			
			.start{
				color: #999;
				    font-size: 10px;
					overflow: hidden;
					text-overflow: ellipsis;
					display: -webkit-box;
					-webkit-line-clamp: 1;
					 -webkit-box-orient: vertical;
					 line-height: 23px;
			}

			.desc {
				margin-top: 10px;
				color: #a2a2b6;
				font-size: 12px;
				line-height: 18px;

				overflow: hidden;
				text-overflow: ellipsis;
				display: -webkit-box;
				-webkit-line-clamp: 3;
				 -webkit-box-orient: vertical;
			}
		}

	}
</style>
<template>
	<!-- <view class="ui-video">
		<view class="card-line" v-if="type == 'line'">
			<view class="left">
				<image class="pic" mode="aspectFill" src="/static/img/other/errorImage.jpg" @error="fun4error" v-if="showError"></image>
				<image class="pic" lazy-load=true mode="aspectFill" :src="obj.pic" @error="fun4error" v-else></image>
				<view class="tip" v-if="config.verify!=1">{{obj.alias}}</view>
			</view>
			<view class="right">
				<view class="name">{{obj.name}}</view>
				<view class="start">主演：{{obj.start}}</view>
				<view class="desc"  > {{obj.introduce}} </view>
			</view>

		</view>

		<view class="card-def" v-else>
			<view class="content">
				<!-- <image class="pic" mode="aspectFill" src="/static/img/other/errorImage.jpg" @error="fun4error" v-if="showError"></image>>
				<video
				class="pic"
				:id="obj.vid"
				:src="obj.play_url_1"
				object-fit="cover"
				controls
				@error="fun4error"
				v-if="playOn"
				>
				</video>
				<image class="pic" lazy-load=true mode="aspectFill" :src="(obj.pic_gif == undefined || obj.pic_gif == '')? obj.pic : obj.pic_gif" @error="fun4error" @click="beginPlay(obj.vid)"  v-else></image>

				<view class="tip" v-if="config.verify!=1">{{obj.alias}}</view>
			</view>
			<view class="name">{{obj.name || obj.title}}</view>
			<view class="desc"  > {{desc}} </view>
		</view>
	</view> -->
	<view class="list">
	<view class="list-item" v-for="(item,index) in obj" :key="index">
	<view class="ui-video">
		<view class="card-line" v-if="type == 'line'">
			<view class="left">
				<image class="pic" mode="aspectFill" src="/static/img/other/errorImage.jpg" @error="fun4error" v-if="showError"></image>
				<image class="pic" lazy-load=true mode="aspectFill" :src="item.pic" @error="fun4error" v-else></image>
				<view class="tip" v-if="config.verify!=1">{{item.alias}}</view>
			</view>
			<view class="right">
				<view class="name">{{item.name}}</view>
				<view class="start">主演：{{item.start}}</view>
				<view class="desc"  > {{item.introduce}} </view>
			</view>
	
		</view>
	
		<view class="card-def" v-else>
			<view class="content">
				<!-- <image class="pic" mode="aspectFill" src="/static/img/other/errorImage.jpg" @error="fun4error" v-if="showError"></image> -->
				<video
				class="pic"
				:id="item.vid"
				:src="item.play_url_1"
				object-fit="cover"
				autoplay
				controls
				@error="fun4error"
				v-if="item.vid === curVid"
				>
				</video>
				<image class="pic" lazy-load=true mode="aspectFill" :src="(item.pic_gif == undefined || item.pic_gif == '')? item.pic : item.pic_gif" @error="fun4error" @click="beginPlay(item.vid)"  v-else></image>
				<view v-if="config.verify!=1" class="storeListVideo">
				  <image v-if="item.vid != curVid" @click="beginPlay(item.vid)"  src="/static/img/other/playmask.png" />
				</view>
				<view v-if="item.vid != curVid" class="tip">{{item.alias}}</view>
				<view class="desc">{{item.name || item.title}}</view>
			</view>
			<view class="viewButtom">
				<view class="viewItem">
				<image  class="typeIcon" src="/static/img/other/playnum.png" />
				<view class="watchNum">{{item.see}}看过</view>
				</view>
				<view class="viewItem">
				<image  class="typeIcon" src="/static/img/other/dianzan.png" />
				<view class="watchNum">{{item.link}}赞</view>
				</view>
				<!-- #ifdef MP-WEIXIN -->
				<view class="viewItem">
				  <button class="shareCommand" open-type="share" :data-vid="item.vid" :data-title="item.name" :data-pic="item.pic">
					  <image  class="wechatIcon" src="/static/img/other/rwechat.png" />
					  <view class="shareNum">{{item.shareNum}}分享</view>
				  </button>
				  </view>
				<!-- #endif -->

				
				</view>
			</view>
			
			<!-- <view class="desc"  > {{desc}} </view> -->
		</view>
	</view>
	</view>
	</view>
</template>

<script>
	import uniIcons from "../plug/uni-icons/uni-icons.vue";
	import { mapActions, mapGetters, mapState } from "vuex"
	import {
		util,
	} from '@/comps/base/index.js'
	export default {
		name: "uiGoods",
		data() {
			return {
				showError: false,
				curVid : '',
				
			}
		},
		components: {
			uniIcons
		},
		props: {
			placeholder: {
				type: String,
				default: "请输入搜索内容"
			},
			type: {
				type: String,
				default: "def"
			},
			 
			obj: {}


		},
		computed: {
			...mapState({
				config(state) {
					return state.start.config
				},
			}),
		 
			desc(){
				// let {obj} = this;
				// 
				// return String.HasText(obj.address)?  [obj.address,obj.year,obj.start].filter(curr=>{
				// 	return String.HasText(curr)
				// }).join("/"):obj.introduce;
				
			}
		},
		methods: {
			async fun4detail(uuid){
				// uni.setStorageSync('shareVideoId',uuid);
				util.jump.navigateTo("/public/films/detail?uuid="+uuid);
				
			},
			async fun4error(e) {
				this.showError = true;
			},
			async beginPlay(vid){
				// emit 自定义事件
				if(this.config.verify == 1){
					return;
				}
				this.curVid = vid;
				this.$emit('playVideo',vid);
				uni.createVideoContext(vid,this).play();
				
				
			},
			async shareWechat(vid){
				
			},
			
			async myPlay(vid){

				
			},


		}
	};
</script>
