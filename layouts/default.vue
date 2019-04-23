<template>
  <v-app >
    <v-content class="contentForm">
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<style>
  .contentForm {
    background-color: white;
    padding: 10px;
  }
</style>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
