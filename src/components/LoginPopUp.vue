<template>
  <div class="login-pop-up">
    <div class="login-child">
      <div>
        <button @click="$emit('closePopUp', product)" class="btn">X</button>
      </div>
      <section>
        <div class="tab">
          <button class="tablincs">Sing In</button>
          <button class="tablincs">Sing Up</button>
        </div>
        <div class="tabcontent">
          <form action="#">
            <label for="">Login</label>
            <input type="text" />
            <label for="">Password</label>
            <input type="text" />
            <button class="but">Sign In</button>
          </form>
        </div>
        <div class="tabcontent">
          <form action="#">
            <label for="">Login</label>
            <input type="text" />
            <label for="">Password</label>
            <input type="text" />
            <label for="">Repeated Password</label>
            <input type="text" />
            <button class="but">Sign In</button>
          </form>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoginPopUp",
  data: () => ({}),
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Rubik&display=swap");
* {
  position: relative;
  padding: 0;
  border: 0;
  margin: 0;
  font-family: "Inter", sans-serif;
  font-size: inherit;
  line-height: inherit;
  color: inherit;
  font-weight: normal;
  text-decoration: none;
  list-style: none;
  border-collapse: collapse;
  border-spacing: 0;
  outline: none;
  -webkit-box-shadow: none;
  box-shadow: none;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  cursor: default;
  -moz-appearance: none !important;
  -webkit-appearance: none !important;
  appearance: none !important;
}

input,
textarea {
  cursor: text;
}

a,
a *,
button,
input[type="range"],
input[type="button"],
input[type="submit"],
input[type="reset"],
input[type="radio"],
input[type="checkbox"] {
  cursor: pointer;
}

article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
nav,
section,
iframe,
a,
img,
form,
label,
ul,
ol {
  display: block;
}

.login-pop-up {
  margin-bottom: 150px;
  position: fixed;
  background: #0008;
  z-index: 30;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.login-child {
  position: absolute;
  z-index: 35;
  overflow: auto;
  background: #fff;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

body {
  display: flex;
  justify-content: center;
}

section {
  margin: auto;
  margin-top: 20%;
}

.tab {
  font-size: 0;
}

.tablincs {
  margin-right: 2px;
  font-size: 14px;
  padding: 0.9375rem 3rem;
  background-color: #96b7dd;
  border-top-left-radius: 0.9375rem;
  border-top-right-radius: 0.9375rem;
  color: white;
  font-size: 0.875rem;
}

.tablincs:last-child {
  margin-right: 0;
}

/* .tablincs-active {
  background-color: #397db4;
} */

.tabcontent {
  /* display: none; */
  padding: 40px 20px;
  box-shadow: 0 2px 5px rgb(0 0 0 / 50%);
}

/* .tabcontent-active {
  display: block;
} */

form {
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 20px;
}

input {
  margin-bottom: 10px;
  border-bottom: 1px solid #c3c3c3;
}

.but {
  margin-top: 40px;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #508cbd;
  color: #508cbd;
}
</style>