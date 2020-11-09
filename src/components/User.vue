<template>
  <div id="user">
    <h2>{{ user.name }}</h2>
    <div id="changeUser">
      <button @click="toogleLoginForm">Alterar usuário</button>
    </div>

    <div id="loginForm" v-show="showLoginForm">
      <a href="#" @click="toogleLoginForm">x</a>
      <input type="text" placeholder="nome*" v-model="nameField" />
      <input type="email" placeholder="email" v-model="emailField" />
      <input type="password" placeholder="senha" v-model="passwordField" />
      <button @focus="changeUser" @click="toogleLoginForm">
        Entrar
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: "Lucas",
        email: "lucasmatheusjung@hotmail.com",
        password: "123321",
      },
      showLoginForm: false,
      nameField: "",
      emailField: "",
      passwordField: "",
    };
  },
  methods: {
    toogleLoginForm: function() {
      this.showLoginForm = !this.showLoginForm;
    },
    changeUser: function() {
      if (this.nameField.trim().length > 0) {
        this.user = {
          name: this.nameField,
          email: this.emailField,
          password: this.passwordField,
        };
      } else {
        alert("Nome inválido!");
      }
      this.nameField = "";
      this.emailField = "";
      this.passwordField = "";
    },
  },
};
</script>
<style scoped>
#user {
  display: flex;
  align-items: center;
  position: absolute;
  top: 5px;
  right: 20px;
}
#user h2 {
  color: rgb(255, 78, 196);
}
#changeUser button {
  color: black;
  font-weight: bold;
  background-color: #36f2ff;
  border: none;
  padding: 7px 20px;
  margin: 0 0 0 20px;
}
#loginForm {
  top: 60px;
  right: 0;
  position: absolute;
  flex-direction: column;
}
#loginForm input {
  font-size: 1.3rem;
  background-color: #212131;
  color: white;
  border: slategrey 1px solid;
  margin: 1px 0;
}
#loginForm button {
  background-color: #72ff56;
  border: 1px solid slategrey;
  font-weight: bold;
}
#loginForm a {
  position: absolute;
  right: -17px;
  top: 1px;
  color: rgb(255, 255, 255);
  background-color: rgb(105, 0, 0);
  padding: 2.5px;
  border: 1px rgb(255, 0, 0) solid;
  text-decoration: none;
}
</style>
