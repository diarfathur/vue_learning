<template>
  <v-layout row column>
    
    <v-flex xs12 text-xs-center>
      <v-carousel hide-controls dark max>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          >
          <img :src="require(`assets/img/${ item.src }`)" class="carousel-images" width="100%">
        </v-carousel-item>
      </v-carousel>
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

<style>
  .carousel-images {
    margin-top: 110px;
  }
</style>


<script>
  export default {
    data () {
      return {
        items: [
          {
            src: 'add_to_cart.png'
          },
          {
            src: 'mobile_apps.png'
          },
          {
            src: 'profile_data.png'
          }
        ]
      }
    },

    methods: {
      login() {
        this.$router.push("/login")
      }
    }
  }
</script>