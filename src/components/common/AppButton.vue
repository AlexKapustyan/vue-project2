<template>
  <div class="app-button">
    <button @click="$emit('appButtonClic')">{{ appButtonText }}</button>
  </div>
</template>

<script>
export default {
  name: "AppButton",
  props: ["appButtonText"],
  data: () => ({}),
};
</script>

<style scoped>
.app-button button {
  padding: 10px 20px;
  font-size: 14px;
  cursor: pointer;
}
</style>