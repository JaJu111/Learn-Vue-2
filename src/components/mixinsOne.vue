<template>
	<div>
		<div class="list-group">
      <h2>All Developers</h2>
			<a href="#" class="list-group-item list-group-item-action">{{ timlit }}</a>
			<a href="#" class="list-group-item list-group-item-action">{{ senior }}</a>
			<a href="#" class="list-group-item list-group-item-action">{{ middle }}</a>
      <a href="#" class="list-group-item list-group-item-action">{{ junior }}</a>
      <a href="#" class="list-group-item list-group-item-action">{{ junior2 }}</a>
      <a href="#" class="list-group-item list-group-item-action">{{ junior3 }}</a>
		</div>
	</div>
</template>

<script>

import ListGroup from '../ListGroup';

export default {
	mixins: [ListGroup],
}

</script>

<style scoped>
	.list-group{
    margin-top: 50px;
  }
  .list-group-item{
    font-size: 20px;
  }
</style>