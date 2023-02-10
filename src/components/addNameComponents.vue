<template>
	<div>
		<div class="list-group">
			<li
				href="#"
				class="list-group-item list-group-item-action active"
			>
				List Name:
			</li>
				<nameComponent
					v-for="(item) in allName"
					:key="item.id"
					:item="item"
					@onRemove="$emit('onRemove', item.id)"
			/>
        </div>
	</div>
</template>

<script>

import nameComponent from './nameComponent.vue'

export default {
	components: {
		nameComponent
	},
	props: {
		allName: {
			type: Array,
			required: true
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