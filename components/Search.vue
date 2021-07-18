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
        <v-text-field v-model="searchQuery" append-icon="mdi-magnify" label="Search for the post" outlined></v-text-field>
        <v-list v-if="articles.length" class="mt-n8">
            <v-list-item-group>
                <v-list-item v-for="article of articles" :key="article.slug">
                    <v-list-item-content>
                        <NuxtLink :to="{name: 'blog-slug', params: {slug: article.slug}}" class="text-decoration-none">{{article.title}}</NuxtLink>
                    </v-list-item-content>
                </v-list-item>
            </v-list-item-group>
        </v-list>
    </div>
</template>