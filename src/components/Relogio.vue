<template>
	<div id="Clockapplication">
		<form name="form_relogio" class="responsive">
			<img class="h-ponteiro" src="../assets/relogio.png">
			<input class="h-digital" type="text" name="relogio" size="10" v-model="hours">
		</form>
	</div>
</template>
<script>
	export default{
   	name:'hora',
   	data(){
   		return{
   			//momentoAtual:'',
   			hours:''
   		}
   	},
   	created(){
   			var momentoAtual = new Date()
   			return this.hours = momentoAtual.getHours() + ':' + momentoAtual.getMinutes()  + ':' + momentoAtual.getSeconds()
   	}
   	// computed:{
   	// 	hours(){
   	// 		var momentoAtual = new Date()
   	// 		return momentoAtual.getHours() + ':' + momentoAtual.getMinutes()  + ':' + momentoAtual.getSeconds()
   	// 	}
   	// }
}
</script>
<style scoped>
	#Clockapplication{
		background-image: url(../assets/fundo.jpg);
		min-height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.responsive{
		display: flex;
		flex-direction: column;
	}
	.h-ponteiro{	
		width: 20vh;
		margin: 0 0 0 80px;		
	}
	.h-digital{
		background: white;
		color: black;
		width: 40vh;
		height: 14vh;
		font-size: 50px;
		margin: 10px;
		text-align: center;
	}
	.data{
		background: white;
		font-size: 30px;
		margin: 10px;
	}
</style>