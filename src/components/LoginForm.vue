<script>
import '../assets/forms.css';
import FormContent from './FormContent.vue';
export default {
  name: 'login',
  data() {
    return {
      email: null,
      password: null,
      userRegistrationInfo: null,
    };
  },
  // methods: {
  //   login(e) {
  //     e.preventDefault();
  //     const getUserInfo = new Promise((resolve, reject) => {
  //       this.userRegistrationInfo = {
  //         email: this.email,
  //         password: this.password,
  //       };
  //       resolve('Retrieved Data!');
  //       reject('Failed to retrieve data!');
  //     });
  //     getUserInfo.then(() => {
  //       fetch('http://127.0.0.1:8000/api/login', {
  //         method: 'POST',
  //         headers: {
  //           Accept: 'application/json',
  //           'Content-Type': 'application/json',
  //         },
  //         body: JSON.stringify({
  //           email: this.userRegistrationInfo.email,
  //           password: this.userRegistrationInfo.password,
  //         }),
  //       })
  //         .then((response) => response.json())
  //         .then((data) => {
  //           console.log('Success:', data);
  //         })
  //         .catch((error) => {
  //           console.error('Error:', error);
  //         });
  //     });
  //   },
  // },
  components: { FormContent },
};
</script>

<template>
  <form>
    <FormContent form-category="login" endpoint="login" />
  </form>
</template>

<style scoped>
form {
  height: 85%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

button {
  margin-bottom: 8rem;
}
</style>
