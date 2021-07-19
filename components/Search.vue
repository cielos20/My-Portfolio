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
    <!-- Need to figure out how to make it appear on the bottom -->
    <v-menu offset-y class="mt-16">
      <template #activator="{on, attrs}">
        <v-text-field v-model="searchQuery" v-bind="attrs" class="mt-6 mr-7" append-icon="mdi-magnify" label="Search for the post" dense outlined v-on="on"></v-text-field>
        <!-- Need to figure out how to trigger a tooltip on search -->
        <v-card  elevation="6">
        <v-list v-if="articles.length" class="mt-16" >
            <v-list-item-group class="mt-16">
                <v-list-item v-for="article of articles" :key="article.slug">
                    <v-list-item-content>
                        <NuxtLink :to="{name: 'blog-slug', params: {slug: article.slug}}" class="text-decoration-none">{{article.title}}</NuxtLink>
                    </v-list-item-content>
                </v-list-item>
            </v-list-item-group>
        </v-list>
        </v-card>
      </template>
    </v-menu>
</template>