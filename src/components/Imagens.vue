<template>
	<div>
		<div v-if="imagem === 'Pedra' ">
			<img src="../assets/Pedra.png"> 
		</div>
		<div v-if="imagem === 'Papel' ">
			<img src="../assets/Papel.png"> 
		</div>

		<div v-if="imagem === 'Tesoura' ">
			<img src="../assets/Tesoura.png">
		</div> 
	</div>
</template>

<script>
	export default{
		name: 'Imagens',
		props: ['imagem']
	}
</script>

<style scoped>
img{
    height: 250px;
    max-width: 300px;
    width: 250px;
}	
</style>
