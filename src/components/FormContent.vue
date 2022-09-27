<template>
  <form>
    <div v-if="formCategory === 'register'" class="form-input">
      <label>Username</label>
      <input type="text" placeholder="mr_bean1" v-model="name" />
    </div>

    <div class="form-input">
      <label>Email</label>
      <input type="email" placeholder="mr_bean@email.com" v-model="email" />
    </div>

    <div class="form-input">
      <label>Password</label>
      <input type="password" placeholder="************" v-model="password" />
    </div>

    <button v-if="formCategory === 'login'" @click="handleFormSubmit">
      Login
    </button>
    <button v-if="formCategory === 'register'" @click="handleFormSubmit">
      Register
    </button>
  </form>
</template>

<script>
import '../assets/forms.css';
export default {
  name: 'FormContent',
  props: {
    endpoint: String,
    formCategory: String,
    // userInfo: Object
  },
  data() {
    return {
      userInfo: null,
    };
  },
  methods: {
    handleFormSubmit(e) {
      let endpoint = this.endpoint;
      e.preventDefault();
      const getUserInfo = new Promise((resolve, reject) => {
        this.userRegistrationInfo = {
          email: this.email,
          password: this.password,
          name: this.name,
        };
        resolve('Retrieved Data!');
        reject('Failed to retrieve data!');
      });
      getUserInfo.then(() => {
        fetch(`http://127.0.0.1:8000/api/${endpoint}`, {
          method: 'POST',
          headers: {
            Accept: 'application/json',
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            email: this.userRegistrationInfo.email,
            password: this.userRegistrationInfo.password,
            name: this.userRegistrationInfo.name,
          }),
        })
          .then((response) => response.json())
          .then((data) => {
            console.log('Success:', data);
            this.userInfo = data;
            console.log('Logging userInfo');
            console.log(this.userInfo);
          })
          .catch((error) => {
            console.error('Error:', error);
          });
      });
      console.log(this.userRegistrationInfo);
    },
  },
};
</script>
