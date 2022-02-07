<template>
  <div class="header">
    <div v-html="logoHtml"></div> 
		<button @click="$emit('loginButtonClick')">LogIn</button>
  </div>
</template>

<script>
export default {
  name: "Header",

  data: () => ({
    logoHtml: "<a href=”/”>MyBlog.com</a>",
  }),
};
</script>

<style scoped>
.header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 20px;
}

button {
	padding: 10px;
}
</style>
