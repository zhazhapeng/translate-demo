<template>
	<div id="translateForm">
		<form id="cen" class="form-inline form-center" v-on:submit="formSubmit">
			<input class="form-control" type="text" v-model="translateText" placeholder="请输入要翻译的内容" >
		<select class="form-control" v-model="language">
			<option value="en" >英语</option>
			<option value="ru">俄语</option>
			<option value="fa" >日语</option>
			<option value="ko">韩语</option>
		</select>
		<input class="btn btn-primary" type="submit" value="翻译" />
		</form>
	</div>
</template>

<script>
export default {
  name:'translateForm',
  data:function(){
  	return{
  		translateText:"",
  		language:""
  	}
  },
  methods: {
  	formSubmit:function(e){
//		alert(this.translateText);
//		事件注册
		this.$emit("formSubmit",this.translateText,this.language);
  		e.preventDefault();
  	}
  },
  created:function(){
  	this.language="en";
  }
}
	
</script>

<style>
	*{
		padding: 0;
		margin: 0;
	}
	#cen{
		position: relative;
		left:38%;
		
	}
</style>