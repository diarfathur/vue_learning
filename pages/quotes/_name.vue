<template>
  <v-layout row wrap>
    <Header />
	<v-flex xs text-xs-center class="mb-2">
        <h2>Quotes</h2>
    </v-flex>
    <v-flex s12 text-xs-center>
      <blockquote class="blockquote">
        &#8220; {{ post.quotes }} &#8221;
        <footer>
          <small>
            <em>&mdash;{{ post.penulis }}</em>
          </small>
        </footer>
      </blockquote>
    
    </v-flex>
    <div class="block text-right">
			<h4>Quotes lainnya:</h4>
			<ul>
				<li v-for="related in otherQuotes" :key="related.name">
					<nuxt-link :to="`/quotes/${related.name}`">
						{{related.name}}
					</nuxt-link>
				</li>
			</ul>
    </div>
  </v-layout>
</template>

<script>
  import Header from "~/components/Header.vue"

  export default {
    components: {
      Header
    },

    data () {
        return {
        name: this.$route.params.name,
        }
    },

    computed: {
        post () {
            return this.$store.state.quotes.all.find(post => post.name === this.name)
        },
        otherQuotes () {
            return this.$store.state.quotes.all.filter(post => post.name !== this.name)
        }
    }
}
</script>
