<script>
  export default {
    data() {
      return {
        searchQuery: '',
        articles: []
      }
    },
    watch: {
      async searchQuery(searchQuery) {
        if (!searchQuery) {
          this.articles = []
          return
        }
        this.articles = await this.$content('articles')
          .limit(6)
          .search(searchQuery)
          .fetch()
      }
    }
  }
</script>


<template>
  <div>
    <!-- Need to make a function that resets the textfield when I click on a link of the searched results -->
    <v-text-field v-model="searchQuery" placeholder="Search Blog articles" class="d-block" full-width append-icon="mdi-magnify" outlined dense></v-text-field>
    <v-list
      v-if="articles.length"
      class="mt-n6"
      style="z-index: 10; position: absolute; width: auto; overflow: hidden; flex: 1 1 0%" elevation="8"
    >
      <v-list-item v-for="article of articles" :key="article.slug">
        <v-list-item-content>
          <NuxtLink
            :to="{ name: 'blog-slug', params: { slug: article.slug } }"
            class="d-flex px-4 primary--text text-decoration-none"
          >
            {{ article.title }}
          </NuxtLink>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>