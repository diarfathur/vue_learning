<template>
  <v-form v-model="valid">
  <v-layout
    row
    wrap
  >
    <v-flex
      xs12
      text-xs-center
    >
      <h2 class="titlePage"> Masuk sebagai Penjual </h2>
    </v-flex>
    <v-flex xs12>
      <v-text-field
        v-model="username"
        label="Username"
        outline
        clearable
        :loading="loading"        
        class="loginField"
        :rules="[rules.username, rules.minUsername]"
      ></v-text-field>
    </v-flex>
    <v-flex xs12>
      <v-text-field
        v-model="password"
        outline
        :loading= "loading"
        :append-icon="showPass ? 'visibility' : 'visibility_off'"
        :rules="[rules.password, rules.minPassword]"
        :type="showPass ? 'text' : 'password'"
        label="Password"
        value=""
        class="loginField"
        @click:append="showPass = !showPass"
      ></v-text-field>
    </v-flex>
    <v-flex
      xs12
      text-xs-right
    >
      <div class="mb-2">
        <a class="redLink" href="">Lupa Password?</a>
      </div>
    </v-flex>
    <v-btn
      class="text-none "
      block
      color="error"
      large
      light
      depressed
      :loading="loading"
      :disabled="!valid || loading"
      @click="submit"
    >
      Masuk
    </v-btn>
    <v-flex xs12 text-xs-center>
      <span>Dengan masuk ke aplikasi ini, Anda telah menyetujui,</span><br/>
      <span><a class="redLink" href="#">Syarat dan Ketentuan</a></span>
      <span> yang berlaku</span>
    </v-flex>
  </v-layout>
  </v-form>
</template>

<style scoped>
  .titlePage {
    color: #51BCB8;
    margin-bottom: 24px;
  }
  
  .redLink {
    color: red;
    margin: 0 0 12px;
    text-decoration: none;
  }

  .loginField >>> .v-input__control .v-input__slot {
    border: 1px solid;
    font-size: 16px;
  }
  
  .loginField >>> .v-text-field__slot input {
    margin-top: 0;
    height: 48px;
    max-height: 48px;
    font-size: 16px;
    padding: 0 5px;
  }

  .loginField >>> .v-text-field__slot .v-label--active {
    -webkit-transform: translateY(-25px) scale(0.75);
    transform: translateY(-25px) scale(0.75);
    background: #fff;
    top: 18px;
    padding: 0 5px;
  }

  .loginField.v-input--is-focused.primary--text >>> .v-label--active,
  .loginField.v-input--is-focused.primary--text >>> i {
    color: #51BCB8 !important;    
  }
  
  .loginField >>> i {
    font-size: 18px;    
  }

  .loginField.v-input--is-focused.primary--text >>> .v-input__slot {
    border: #51BCB8 1px solid;
  }

  .loginField >>> .v-progress-linear__bar__indeterminate {
    background: #51BCB8 !important;
  }
</style>



<script>
  export default {
    data () {
      return {
        username: '',
        password: '',
        valid: true,
        loading: false,
        showPass: false,
        rules: {
          password: value => !!value || 'Kata sandi harus diisi',
          minPassword: v => v.length >= 3 || 'Password harus lebih dari 3 karakter',
          username: v => !!v || 'Username harus diisi',
          minUsername: v => (v && v.length >= 3) || 'Username harus lebih dari 3 karakter',
        }
      }
    },

    methods: {
      submit() {
        this.loading = true
        setTimeout(() => {
          this.loading = false
          this.$router.push("/afterLogin")
        }, 2000)
      }
    }
  }
</script>
