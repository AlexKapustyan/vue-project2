<template>
  <div class="sign-up-page">
    <h3 class="sign-up-page__title">Sign Up Page</h3>
    <form class="sign-up-page__form">
      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'name' }"
      >
        <label>User Name</label>
        <input
          type="text"
          v-model.lazy="userInfo.name"
          @focus="setActiveItem('name')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'surname' }"
      >
        <label>User Surname</label>
        <input
          type="text"
          v-model.lazy="userInfo.surname"
          @focus="setActiveItem('surname')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'email' }"
      >
        <label>User email</label>
        <input
          type="text"
          v-model.trim="userInfo.email"
          @focus="setActiveItem('email')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'phone' }"
      >
        <label>User phone</label>
        <input
          type="number"
          v-model.number="userInfo.phone"
          @focus="setActiveItem('phone')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'birthYear' }"
      >
        <label>User birth Year</label>
        <input
          type="number"
          v-model.number="userInfo.birthYear"
          @focus="setActiveItem('birthYear')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'genderFemale' }"
      >
        <label>User gender Female</label>
        <input
          type="radio"
          value="female"
          v-model.number="userInfo.gender"
          id="female"
          @focus="setActiveItem('genderFemale')"
        />
        <label for="female">Female</label>
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'genderMale' }"
      >
        <label>User gender Male</label>
        <input
          type="radio"
          value="male"
          v-model.number="userInfo.gender"
          id="male"
          @focus="setActiveItem('genderMale')"
        />
        <label for="male">Male</label>
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'logIn' }"
      >
        <label>User logIn</label>
        <input
          type="text"
          v-model.trim="userInfo.logIn"
          @focus="setActiveItem('logIn')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'password' }"
      >
        <label>User password</label>
        <input
          type="text"
          v-model.trim="userInfo.password"
          @focus="setActiveItem('password')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'repeatedPassword' }"
      >
        <label>User repeated password</label>
        <input
          type="text"
          v-model.trim="userInfo.repeatedPassword"
          @focus="setActiveItem('repeatedPassword')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'commercialExperience' }"
      >
        <label>User commercial experience</label>
        <input
          type="checkbox"
          v-model="userInfo.commercialExperience"
          true-value="Yes, I have"
          false-value="No, I haven`t"
          @focus="setActiveItem('commercialExperience')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'yearsOfExperience' }"
      >
        <label>User years of experience</label>
        <input
          type="number"
          v-model.number="userInfo.yearsOfExperience"
          id="yearsOfExperience"
          v-show="userInfo.commercialExperience === 'Yes, I have'"
          @focus="setActiveItem('yearsOfExperience')"
        />
        <label for="yearsOfExperience">How many years do you have?</label>
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'country' }"
      >
        <label>User Country</label>
        <input
          type="text"
          v-model.lazy="userInfo.country"
          @focus="setActiveItem('country')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'city' }"
      >
        <label>User City</label>
        <input
          type="text"
          v-model="userInfo.city"
          v-if="userInfo.country !== 'Ukraine'"
          @focus="setActiveItem('city')"
        />

        <select v-else v-model="userInfo.city">
          <option value="" disabled>City</option>
          <option v-for="(city, index) in ukrainianCities" :key="index">
            {{ city }}
          </option>
        </select>
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'address' }"
      >
        <label>User address</label>
        <input
          type="text"
          v-model="userInfo.address"
          @focus="setActiveItem('address')"
        />
      </div>

      <div
        class="sign-up-page__form-item"
        :class="{ active: isActive === 'englishLevel' }"
      >
        <label> English level: </label>
        <select v-model="userInfo.englishLevel">
          <option value="" disabled>English level</option>
          <option
            :value="level.value"
            v-for="(level, index) in englishLevelsValues"
            :key="index + level.value"
          >
            {{ level.label }}
          </option>
        </select>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "SignUp",
  data: () => ({
    userInfo: {
      name: "",
      surname: "",
      email: "",
      phone: null,
      birthYear: null,
      gender: null,
      logIn: "",
      password: "",
      repeatedPassword: "",
      commercialExperience: null,
      yearsOfExperience: null,
      country: "",
      city: "",
      address: "",
      englishLevel: "",
    },
    englishLevelsValues: [
      {
        value: "A1",
        label: "Beginner",
      },
      {
        value: "A2",
        label: "Elementary",
      },
      {
        value: "B1",
        label: "Intermediate",
      },
      {
        value: "B2",
        label: "Upper Intermediate",
      },
      {
        value: "C1",
        label: "Advanced",
      },
      {
        value: "C2",
        label: "Proficiency",
      },
    ],
    isActive: "",
  }),
  setActiveItem(activeInput) {
    this.isActive = activeInput;
  },
};
</script>

<style scoped lang="scss">
.sign-up-page {
  display: flex;
  flex-direction: column;
  width: 500px;
  margin-left: 35%;
  margin-top: 1%;
  padding: 20px;
  border: 1px solid rgb(73, 73, 223);
  background-color: rgb(73, 73, 223);
  color: #fff;
  border-radius: 10px;
}

.sign-up-page__title {
  font-size: 30px;
  text-align: center;
}

.sign-up-page__form {
  display: flex;
  flex-direction: column;
  padding: 0 50px;
}

.sign-up-page__form-item {
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}

#editing-view-port {
  margin: 0 10px 0 10px;
}
</style>


