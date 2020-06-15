<template>
  <div>
    <v-container>
      <v-flex xs12 pb-5>
        <h2>News</h2>
      </v-flex>

      <v-flex>
        <!--News-->
        <v-flex xs12 pb-3 sm6 offset-sm3 v-for="(article, index) in articles" :key="index"><v-card>
            <img :src="article.urlToImage" width="100%" height="200px">
            <v-card-title>{{article.title}}</v-card-title>
            <v-card-text> {{article.content}}</v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn text :href="article.url" target="_blank">Open</v-btn>
              <v-spacer></v-spacer>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-flex>
    </v-container>
  </div>
</template>

<script>
    export default {
        async asyncData({app}) {
            const {articles} = await app.$axios.$get('http://newsapi.org/v2/top-headlines?country=us&category=business&apiKey=b4b30c8d5ac9458b970abab6b2b08e40');
            return {articles};
        }
    }
</script>

<style scoped>

</style>
