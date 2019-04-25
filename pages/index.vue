<template>
  <v-layout row column>
    
    <v-flex xs12 text-xs-center>
      <blockquote class="blockquote">
        &#8220;INI HALAMAN HOME&#8221;
        <footer>
          <small>
            <em>&mdash;GUDANG ADA</em>
          </small>
        </footer>
      </blockquote>
    </v-flex>
    <v-flex xs12 text-xs-center>
    <v-btn
      class="text-none "
      color="error"
      large
      light
      depressed
      @click="login"
      :loading="loading"
    >
      Masuk
    </v-btn>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    methods: {
      login() {
        this.$router.push("/login")
      }
    }
  }
</script>