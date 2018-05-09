<template>
	<div id="Clockapplication">
		<!-- <img class="chapeu" src="../assets/chapeu.png"> -->
    	<h1 class="h-digital">{{aTime}}</h1>
    	<div class="container-calendar">
    		<h2 class="calendar">09 de maio de 2018</h2>
    	</div>
    	<p class="restriçao">(Essa óbra de arte feita por um aluno do VainaWeb chamado Marco Gomez)</p>
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
*{
	margin: 0;
	padding: 0;
}
	#Clockapplication{
		background-color: black;	
		/*background-image: url(../assets/bomba.jpg);*/
		min-height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	#Clockapplication:hover{
		background: black;
	}
	.h-digital{
		background: black;
		color: white;
		width: 100vh;
		height: 30vh;
		font-size: 150px;
		text-align: center;
	}
	.calendar{
		background: black;
		color: white;
		/*border:solid;*/
		/*border-width: 3px;*/
		padding: 10px;
		/*border-color: green;*/
		/*border-radius: 50px;*/
	}
	.restriçao{
		background-color: black;
		color: white;
	}
</style>