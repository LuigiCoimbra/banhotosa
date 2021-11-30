<style>
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@700&display=swap');@import url('https://fonts.googleapis.com/css2?family=News+Cycle:wght@700&display=swap');
  .hexagonal1 {
    width: 25px;
    height: 25px;
    top: 0.5px;
    left: 13.9px;
    background: rgba(5,113,142,1);
    transform: rotate(45deg);
    position: relative;
    margin: 0;
  }
  .hexagonal2 {
    width: 25px;
    height: 25px;
    top: 0.5px;
    left: -13.9px;
    background: rgba(54,156,160,1);
    transform: rotate(45deg);
    position: relative;
  }
  .btnhex {
    position: relative;
    background: linear-gradient(90deg, rgba(5,113,142,1) 0%, rgba(54,156,160,1) 100%);
    color: white;
    border-radius: 0px;
  }
</style>

<template>
  <v-app style="display: flex; justify-content: center; align-items: center;">
    <div class="mx-auto mt-auto mb-15 text-center">
      <v-img
    width="350"
    src="../assets/logo-tudo-de-bicho.svg">
    </v-img>
      <span class="mx-auto">Mais facilidade para marcar o<br> banho do seu pet</span>
    </div>
    <v-card width="80vw" class="mx-auto my-auto mt-1">
      <v-card-title class="px-auto mx-auto" style="justify-content: center;">Acessar</v-card-title>
      <v-card-text class="mb-5">
        <v-form>
          <v-text-field label="Email" v-model="email" prepend-icon="mdi-account"></v-text-field>
          <v-text-field
          prepend-icon="mdi-key"
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Normal with hint text"
            hint="At least 8 characters"
            counter
            @click:append="show1 = !show1"
          ></v-text-field>
        </v-form>
      </v-card-text>
      <v-card-actions class="mt-n6">
        <span class="hexagonal1"></span>
        <v-btn
        class="btnhex"
        text
        color="white"
        width="40%"
        >
          <v-icon left>mdi-login</v-icon>
          <span>Entrar</span>
        </v-btn>
        <span class="hexagonal2"></span>
      </v-card-actions>
    </v-card>
  </v-app>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      show1: false,
      password: '',
      rules: {
        required: (value) => !!value || 'Required.',
        min: (v) => v.length >= 8 || 'Min 8 characters',
        emailMatch: () => ('The email and password you entered don\'t match'),
      },
    };
  },
};
</script>
