<template>
  <div id="app" class="app">
		<Header />
    <!-- <post-page/> -->
    <!-- <sign-up /> -->
    <post-list />
    <AppPopUp
      v-if="show"
      @closePopUpEven="closePopUpEven"
      @backPopUpEvent="backPopUpEvent"
      @continuePopUpEvent="continuePopUpEvent"
    />
    <AppButton @appButtonClic="appButtonClic" />
		<LoginPopUp v-if="show" @closePopUp="closePopUp"/>
		<Footer />
  </div>
</template>

<script>
// import PostPage from "./components/PostPage.vue";
// import SignUp from "./components/SignUp.vue";
import PostList from "./components/PostList.vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import LoginPopUp from "./components/LoginPopUp.vue"

export default {
  name: "App",
  components: {
		Header,
		Footer,
    // PostPage,
    // SignUp,
    PostList,
    AppPopUp: () => import("./components/common/AppPopUp.vue"),
		LoginPopUp,
  },

  data: () => ({
    show: true,
  }),

  methods: {
    closePopUpEven() {
      this.show = false;
      console.log("closePopUpEvent");
    },
    backPopUpEvent() {
      console.log("backPopUpEvent");
    },
    continuePopUpEvent() {
      console.log("continuePopUpEvent");
    },
    appButtonClic() {
      console.log("appButtonClic");
    },
		closePopUp(event) {
      this.show = false;
      console.log(event);
    },
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.app {
  /* //text-align: center; */
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 10px 100px 10px 100px;

}
</style>
