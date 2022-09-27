<script>
import '../assets/forms.css';
import FormContent from './FormContent.vue';
export default {
  name: 'register',
  data() {
    return {
      name: null,
      email: null,
      password: null,
      userRegistrationInfo: null,
      inputs: { name: this.name, email: this.email, password: this.password },
      userInfo: null
    };
  },
  // methods: {
  //   register(e) {
  //     e.preventDefault();
  //     const getUserInfo = new Promise((resolve, reject) => {
  //       this.userRegistrationInfo = {
  //         email: this.email,
  //         password: this.password,
  //         name: this.name,
  //       };
  //       resolve('Retrieved Data!');
  //       reject('Failed to retrieve data!');
  //     });
  //     getUserInfo.then(() => {
  //       fetch('http://127.0.0.1:8000/api/register', {
  //         method: 'POST',
  //         headers: {
  //           Accept: 'application/json',
  //           'Content-Type': 'application/json',
  //         },
  //         body: JSON.stringify({
  //           email: this.userRegistrationInfo.email,
  //           password: this.userRegistrationInfo.password,
  //           user: this.userRegistrationInfo.user,
  //         }),
  //       })
  //         .then((response) => response.json())
  //         .then((data) => {
  //           console.log('Success:', data);
  //           this.userInfo = data;
  //         })
  //         .catch((error) => {
  //           console.error('Error:', error);
  //         });
  //     });
  //     console.log(this.userRegistrationInfo);
  //   },
  // },
  components: { FormContent },
};
</script>

<template>
  <form>
    <FormContent
      form-category="register"
      endpoint="register"
      v-model="inputs.email"
    />
  </form>
</template>

<style scoped>
form {
  height: 85%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
</style>
