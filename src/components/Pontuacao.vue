<template>
	<div>
		<h1>
			{{ pontuacaoUser }} - {{ pontuacaoMach }}
		</h1>
	</div>
</template>

<script>
export default{
	name: 'Pontuacao',
	props: {
		pontuacaoUser: Number,
		pontuacaoMach: Number,
	}
}

</script>

<style scoped>

</style>