<template>
  <div id="app" class="app">
    <div class="app-head">
      <Header class="header" @loginButtonClick="showLoginPopUp = true" />
      <!-- <button class="popup-show" @click="show = true">Sign up</button> -->

      <LoginPopUp v-if="showLoginPopUp" @closePopUp="closePopUp" />
    </div>
    <div class="app-body">
      <!-- <post-page /> -->
      <!-- <sign-up /> -->
      <post-list />
      <AppPopUp
        v-if="showPopUpEvent"
        @closePopUpEvent="closePopUpEvent"
        @backPopUpEvent="backPopUpEvent"
        @continuePopUpEvent="continuePopUpEvent"
      />
      <AppButton @appButtonClic="backPopUpEvent('appButtonMessage')" />
    </div>

    <Footer />
  </div>
</template>

<script>
// import PostPage from "./components/PostPage.vue";
// import SignUp from "./components/SignUp.vue";
import PostList from "./components/PostList.vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import LoginPopUp from "./components/LoginPopUp.vue";

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
    showPopUpEvent: true,
    showLoginPopUp: false,
  }),

  methods: {
    closePopUpEvent() {
      this.showPopUpEvent = false;
      console.log("closePopUpEvent");
    },
    backPopUpEvent() {
      this.showPopUpEvent = true;
      console.log("backPopUpEvent");
    },
    continuePopUpEvent() {
      console.log("continuePopUpEvent");
    },
    appButtonClic() {
      console.log("appButtonClic");
    },
    loginButtonClick() {
      this.showLoginPopUp = true;
    },
    closePopUp() {
      this.showLoginPopUp = false;
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
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 10px 100px 10px 100px;
}

.app-head {
  width: 100%;
}

.popup-show {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 14px;
  cursor: pointer;
}
</style>
