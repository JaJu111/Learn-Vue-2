<template>
	<div>
		<div class="input-group mb-5">
			<input
				type="text"
				:class="[
					'form-control',
					{
						error: hasError
					}
				]"
				placeholder="Add name..."
				:value="name"
				@keyup.enter="addName"
				@input="changeInputValue"
			>

			<div class="input-group-append">
				<button
					class="btn btn-primary"
					type="button"
					@click="addName"
				>
					Add Name
				</button>
			</div>
        </div>
	</div>
</template>

<script>

export default {
	data() {
		return {
			name: '',
			hasError: false
		}
	},
	methods: {
		addName() {
			const newName = {
				name: this.name,
				id: Date.now(),
			}
			if (!this.name.trim().length) {
				this.hasError = true
				return this.$emit('errorInput', true)
			}
			this.$emit('errorInput', false)
			this.$emit('createName', newName)
			this.name = ''
		},
		changeInputValue(event) {
			this.name = event.target.value
			this.$emit('errorInput', false)
			this.hasError = false
		}
	}
}

</script>

<style scoped>
	.form-control{
		font-size: 25px;
	}
	.error {
		border: 1px solid red;
	}
	.btn{
		font-size: 25px;
	}
</style>