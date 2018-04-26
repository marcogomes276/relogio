<template>
	<div id="Clockapplication">
		<img class="chapeu" src="../assets/chapeu.png">
    	<h1 class="h-digital">{{aTime}}</h1>
    	<p class="restriçao">(Esse relogio foi feito por um aluno do VainaWeb chamado Marco Gomez)</p>
	</div>
</template>
<script>
  var getAtime = function() {
  var date = new Date();
  var hour = (date.getHours() < 10) ? '0' + date.getHours() : date.getHours();
  var minute = (date.getMinutes() < 10) ? '0' + date.getMinutes() : date.getMinutes();
  var second = (date.getSeconds() < 10) ? '0' + date.getSeconds() : date.getSeconds();
  var str_hour = hour + ':' + minute + ':' + second;
  return str_hour;
};

	export default{
   	name:'hora',
   	data: function() {
    return {
      time: '00:00:00'
    };
  },		
	 computed: {
		aTime: function() {
		  var self = this;
		  setInterval(function() {
		    self.time = getAtime();
		  }, 1000);
		  return self.time;
		}
	}
}
</script>
<style scoped>
	#Clockapplication{
		background-image: url(../assets/fundo2.jpg);
		/*background-color: black;	*/
		min-height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	#Clockapplication:hover{
		background-image: url(../assets/fundo.jpg);
	}
	.chapeu{
		display: flex;
		justify-content: center;
		align-items: center;
		width: 11em;
		height: 10em;
	}
	.h-digital{
		background: white;
		color: black;
		width: 100vh;
		height: 30vh;
		font-size: 150px;
		text-align: center;
		border:solid;
		border-color: blue;
	}
	.h-digital:hover{
		border:solid;
		border-color: red;
		background-color: black;
		color: white;
	}
	.restriçao{
		background: blue;
		color: white;
		font-size: 2em;
		height: 2em;
		margin: 10px;
		padding: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 50px;
	}
	.restriçao:hover{
		background: red;
		color: black;
		font-size: 2em;
		height: 2em;
		margin: 10px;
		padding: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 50px;

	}
</style>