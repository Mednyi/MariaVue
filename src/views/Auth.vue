<template lang="pug">
.auth
  form.form.auth__form
    h2.form__header {{heading}}
    h4.form_date {{new Date().toLocaleDateString()}}
    input.input.form__input(v-model='user.email' placeholder='E-mail')
    input.input.form__input(v-model='user.password' placeholder='Password')
    .buttons.form_buttons
      button.button(@click.stop="login") {{loginText}}
      button.button(@click.stop="register") {{registerText}}
</template>

<script>
export default {
  name: 'Register-Auth',
  data() {
    return {
      heading: 'ITTasks',
      loginText: 'Войти',
      registerText: 'Регистрация',
      user: {
        email: undefined,
        password: undefined,
      },
    };
  },
  methods: {
    login() {
      const users = JSON.parse(localStorage.users);
      // eslint-disable-next-line max-len
      const foundUser = users.some((user) => user.email === this.user.email && user.password === this.user.password);
      console.log(foundUser);
    },
    register() {
      const users = localStorage.users ? JSON.parse(localStorage.users) : [];
      users.push(this.user);
      localStorage.users = JSON.stringify(users);
    },
  },
};
</script>

<style scoped lang="scss">
h4.form_date {
  margin: 0;
}
.auth {
  grid-area: m;
  display: flex;
  align-items: center;
  justify-content: center;
}
.buttons.form_buttons[data-v-1633063c] {
  display: flex;
  justify-content: space-between;
  margin-top: 32px;
}
form.form.auth__form {
  padding: 32px;
  display: grid;
  grid-gap: 16px;
  min-width: 256px;
  text-align: center;
}
input.input.form__input {
  height: 32px;
  border: none;
  border-bottom: 2px solid;
  text-align: center;
  font-size: 16px;
  outline: none;
}
button.button {
  height: 32px;
  min-width: 112px;
  background-color: #0f62fe;
  border: none;
  color: white;
  outline: none;
}
</style>
