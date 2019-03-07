<template>
	<div class="c">
		<div class="content">
			<select class="c" v-model="selected">
				<option disabled > 请选择</option>
				<option>杭州</option>
				<option>广州</option>
				<option>长沙</option>
			</select>
			<span class="c" @click="click(selected)">提交</span>
			<h1>{{name}}</h1>
			<input type="" name="" v-model="co">
		</div>
	</div>
</template>
<script type="text/javascript">
	import {mapActions,mapMutations} from "vuex"

	export default{
		props:['name'],
		data(){
			return {
				selected:'',
				co:''
			}
		},
		methods:{
			click(city){
				// this.$store.dispatch('changeCity',city)
				this.changeCity(city)
			},
			// ...mapActions(['changeCity'])
			...mapMutations(['changeCity'])
		},
		watch:{
			co(newValue){
				this.$emit('update:name',newValue)
			}
		}
	}
</script>
<style type="text/css">
	
</style>