<template>
  <v-layout column>
    <Header />
    <v-flex xs text-xs-center class="mb-2">
        <h2>My Profile</h2>
        <v-card>
          <v-img
            src="https://upload.wikimedia.org/wikipedia/commons/3/37/No_person.jpg"
          ></v-img>
        </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import Header from "~/components/Header.vue"

  export default {
    components: {
      Header
    }
  }
</script>
