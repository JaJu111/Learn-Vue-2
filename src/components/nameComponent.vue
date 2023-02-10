<template>
	<div>
		<li
			href="#"
			class="list-group-item list-group-item-action">
				{{ item.name }}
			<i
				class="fa-solid fa-xmark"
				@click="$emit('onRemove', item.id)"
			>
			</i>
		</li>
	</div>
</template>

<script>

export default {
	name:'nameComopnent',
	props: {
		item: {
			type: Object,
			required: true,
		}
	}
}

</script>

<style scoped>
	.list-group-item{
		display: flex;
		justify-content: space-between;
		font-size: 25px;
	}
	.fa-solid{
		font-size: 35px;
		cursor: pointer;
	}
</style>