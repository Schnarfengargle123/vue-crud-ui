<template>
  <main>
    <h1>Welcome to the Dashboard!</h1>
  </main>
</template>

<script>
export default {
  props: {
    userInfo: Object,
  },
  data() {
    return {
      userInfo: this.userInfo
    };
  },
  methods: {
    getCurrentUser() {
      fetch(`http://127.0.0.1:8000/api/profile`, {
        method: 'GET',
        headers: {
          Accept: 'application/json',
          'Content-Type': 'application/json',
        },
        // body: JSON.stringify({
        //   email: this.userRegistrationInfo.email,
        //   password: this.userRegistrationInfo.password,
        //   name: this.userRegistrationInfo.name,
        // }),
      })
        .then((response) => response.json())
        .then((data) => {
          console.log('Success:', data);
          console.log(this.userInfo);
        })
        .catch((error) => {
          console.error('Error:', error);
        });
      // console.log(userInfo);
    },
  },
  mounted() {
    this.getCurrentUser();
  },
};
</script>

<style scoped></style>
