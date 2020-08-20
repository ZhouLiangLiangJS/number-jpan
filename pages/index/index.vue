<template>
	<view class="content">
		<button type="default" @tap="open()">弹出吧小宝贝</button>
		<view class="" v-if="text!=''">
			我输入的内容为：{{text}}
		</view>
		<number-jpan :length="6" @closeChange="closeChange($event)" ref="numberPad"></number-jpan>
	</view>
</template>

<script>
	import numberJpan from "@/components/numberJpan/numberJpan.vue";
	export default {
		components:{
			'number-jpan':numberJpan
		},
		data() {
			return {
				text:''
			}
		},
		onLoad() {

		},
		methods: {
			open(){
				this.$refs.numberPad.open()//打开数字输入框
				//this.$refs.numberPad.close()//关闭数字输入框
			},
			closeChange(res){
				console.log({res})
				this.text=res
			}
		}
	}
</script>
