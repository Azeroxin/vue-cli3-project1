<template>
	<div>
		<div v-if="kk==1">
			<GoodsList :goodId="1"></GoodsList>
		</div>
		<div v-else-if="kk==2">
			<GoodsList :goodId="2"></GoodsList>
		</div>
		<div v-else-if="kk==3">
			333
		</div>
		<div v-else-if="kk==4">
			444
		</div>
		<div v-else>
			<GoodsList :goodId="0"></GoodsList>
		</div>
	</div>
</template>
<script type="text/javascript">
	import Msg from './msg.js'
	import GoodsList from './GoodsList.vue'
	export default{
		data(){
			return{
				kk:0
			}
		},
		mounted:function(){
			var  _this=this
			Msg.$on('val',function(m){
				_this.kk=m;
			})

		},
		components:{
			GoodsList
		}
	}
</script>