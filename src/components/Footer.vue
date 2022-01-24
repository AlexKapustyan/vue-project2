<template>
  <div class="footer">
    <div v-html="linkToMyProfile"></div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data: () => ({
    linkToMyProfile:
      '<p>Created by <a href="https://github.com/AlexKapustyan">me</a></p>',
  }),
};
</script>

<style scoped>
	.footer {
		font-size: 20px;
	}
</style>