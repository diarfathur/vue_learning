<template>
  <v-layout row wrap>
    <Header />
    <v-flex xs text-xs-center class="mb-2">
        <h2>News Feed</h2>
    </v-flex>
    <v-flex s12>
      <v-card class="mb-3" v-for="news in listNews" :key="news.title">
        <div v-if="news.urlToImage !== null">
            <v-img
                :src="news.urlToImage"
            ></v-img>
        </div>
        <div v-else>
            <v-img
                src="http://www.lab.hamzanwadi.ac.id/asset/foto_berita/no-image.jpg"
            ></v-img>
        </div>
        <v-card-title primary-title>
            <div>
                <h2>{{ news.title }}</h2>
                <small>{{ news.description }}</small>
            </div>
            <small> <b>News Source:</b> {{ news.source.name }} </small>
        </v-card-title>
        <v-card-actions>
            <v-btn
            align-end
            class="text-none float-right"
            flat
            color="orange"
            :href="news.url"
            >Read on {{ news.source.name }} </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import Header from "~/components/Header.vue"
  import axios from 'axios'

  export default {
    components: {
      Header
    },

    async asyncData ({params}) {
        const { data } = await axios.get(`https://newsapi.org/v2/everything?q=pemilu&pageSize=10&apiKey=21cb00a9a556488e885e52dad8267ff7`)
        return { listNews:data.articles }
    },
}
</script>
