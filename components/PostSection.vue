<template>
<!-- Style this better -->
    <div>
         <h1 class="text-center text-h3 font-weight-medium">Latest posts</h1>
        <v-row justify="center" class="mt-16 px-sm-16 px-2">
            <v-col v-for="article of articles" :key="article.slug" cols="12" sm="6" md="4">
                <v-card elevation="6" class="px-5 py-5">
                    <v-card-title class="primary--text text-break">{{article.title}}</v-card-title>
                    <v-card-title class="primary--text">{{formatDate(article.createdAt)}}</v-card-title>
                    <v-card-text class="text-break">{{article.description}}</v-card-text>
                    <v-btn outlined color="primary" class="ml-3">
                        <NuxtLink :to="{name: 'blog-slug', params: {slug: article.slug}}" class="text-decoration-none">Read more</NuxtLink>
                    </v-btn>
                </v-card>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    data() {
        return {
            articles: []
        }
    },
    async fetch() {
        this.articles = await this.$content('articles')
        .limit(3)
        .only(['title', 'slug', 'createdAt', 'description'])
        .sortBy('createdAt', 'asc')
        .fetch()
    },
    methods: {
        formatDate(date) {
            const options = {year: 'numeric', month: 'long', day: 'numeric'}
            return new Date(date).toLocaleDateString('en', options)
        }
    }
}
</script>