<template>
	<div>
	<button class="button" @click="escolha" >
		{{ opcao }}
	</button>

	</div>
</template>

<script>
export default {
	name: 'Butoes',
	props: {
		opcao: String
	},
	methods: {
		escolha(){
			this.$emit('escolhido',this.$props.opcao)
		}
	}
}
</script>

<style scoped>
  .button {
  background-color: #4CAF50; /* Green background */
  border: 1px solid green; /* Green border */
  color: white; /* White text */
  padding: 20px 44px; /* Some padding */
  cursor: pointer; /* Pointer/hand icon */
  float: left; /* Float the buttons side by side */
}

.button:not(:last-child) {
  border-right: none; /* Prevent double borders */
}

/* Clear floats (clearfix hack) */
.button:after {
  content: "";
  clear: both;
  display: table;
}

/* Add a background color on hover */
.button:hover {
  background-color: #3e8e41;
}
</style>