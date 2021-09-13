<template>
	<div class="file">
		<svg viewBox="0 0 24 24">
			<path fill="currentColor"
				d="M14,17H7V15H14M17,13H7V11H17M17,9H7V7H17M19,3H5C3.89,3 3,3.89 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V5C21,3.89 20.1,3 19,3Z" />
		</svg>
		<span>{{name}}</span>
	</div>
</template>

<script>
	export default {
		name: 'FileView',
		props: {
			name: String
		}
	}
</script>

<style scoped lang="scss">
	.file {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		color: green;
		margin-bottom: 10px;
		width: 200px;

		svg {
			height: 100px;
		}
	}
</style>