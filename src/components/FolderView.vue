<template>

	<details class="folder">
    	<summary class="folder-name">
			<span>{{name}}</span>
			<svg viewBox="0 0 24 24">
				<path fill="currentColor"
					d="M10,4H4C2.89,4 2,4.89 2,6V18A2,2 0 0,0 4,20H20A2,2 0 0,0 22,18V8C22,6.89 21.1,6 20,6H12L10,4Z" />
			</svg>
		</summary>
    	
		<template v-for="folder in folders" :key="folder.name">
			<FolderView :name="folder.name" :folders="folder.folders" :files="folder.files" />
		</template>
		<div class="files-container">
			<template v-for="file in files" :key="file.name">
				<FileView :name="file.name" />
			</template>
		</div>
	</details>
</template>

<script>
	import FileView from "./FileView";
	export default {
		name: 'FolderView',
		components: {
			FileView
		},
		props: {
			name: String,
			folders: Array,
			files: Array
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	.folder {
		border: 1px solid #333;
		margin: 10px 4px;
		color: orangered;
		padding: 10px 0px;
		overflow: hidden;
	}

	.folder-name {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		cursor: pointer;
		height: 150px;
		font-size: 1.2rem;

		svg {
			height: 120px;
		}
	}

	.files-container {
		display: flex;
		flex-wrap: wrap;
	}
	
</style>