<!-- eslint-disable vue/multi-word-component-names -->
<template>
	<div>
    <h1>
      {{ allTitle }}
    </h1>
		<input
      type="text"
      class="form-control"
      placeholder="Search name..."
      :value="allNameFilter"
      @input="changeInputHandler"
    >
	</div>
</template>

<script>

export default {
  props: {
    updateAllNameHandler: {
      type: Function,
      required: true,
    }
  },
	data() {
    return {
      TitleSearch: 'Search',
      TitleName: 'Name',
      allNameFilter: '',
    }
  },
  methods: {
    changeInputHandler(event) {
      this.allNameFilter = event.target.value
      this.updateAllNameHandler(this.allNameFilter)
    }
  },
  computed: {
    allTitle() {
      return this.TitleSearch + ' ' + this.TitleName
    }
  }
}

</script>

<style scoped>
	.form-control{
    margin-bottom: 40px;
    font-size: 25px;
  }
</style>