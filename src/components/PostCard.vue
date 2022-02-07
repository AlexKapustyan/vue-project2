<template>
  <div class="post-card" v-if="post">
    <h1>{{ post.title }}</h1>
    <p>{{ post.body.slice(0, 120) }}</p>
    <button>Read more</button>
  </div>
</template>

<script>
export default {
  name: "PostCard",
  props: {
    post: {
      type: Object,
      required: true,
      default: function () {
        return {
          userId: 1,
          id: 1,
          title: "Some default title",
          body: "Some default text",
        };
      },
      validator: function (value) {
        return Boolean(value.title.length && value.body.length);
      },
    },
  },
  data: () => ({}),
};
</script>

<style scoped>
.post-card p {
  font-size: 20px;
}

.post-card button {
  font-size: 20px;
  border: 0;
  background-color: #fff;
  padding: 0;
  color: #4b97ce;
  cursor: pointer;
}
</style>
