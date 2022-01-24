<template>
  <div class="header">
			<div v-html="logoHtml"></div>
	</div>
</template>

<script>
export default {
  name: "Header",
  data: () => ({
		logoHtml: '<a href=”/”>MyBlog.com</a>',
	}),
};
</script>

<style scoped>
	.header {
		font-size: 20px;
	}
</style>
