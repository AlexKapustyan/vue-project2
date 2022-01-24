<template>
  <div class="app-pop-up">
    <div class="header">
      <button @click="$emit('closePopUpEven')">X</button>
    </div>

    <div class="main"></div>

    <div class="footer">
      <button class="back" @click="$emit('backPopUpEvent')">Back</button>
      <button class="continue" @click="$emit('continuePopUpEvent')">
        Continue
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppPopUp",
  data: () => ({}),
};
</script>

<style scoped>
.app-pop-up {	
	margin-top: 100px;
	max-width: 600px;
	border: 1px solid #000;
	padding: 10px;
	margin-bottom: 20px;
	
}

.header {
  display: flex;
  justify-content: end;
	margin-bottom: 20px;
}

.header button {
  cursor: pointer;
}

.footer {
	display: flex;
	justify-content: center;
}

.footer button {
	min-width: 105px;
	padding: 10px 20px;
	font-size: 14px;
	cursor: pointer;
}

.back {
	margin-right: 20px;
}
</style>