<template>
    <v-row class="mt-16">
        <v-col>
            <v-row class="mt-16" justify="center">
                <h1>Blog Posts</h1>
            </v-row>
            <v-row justify="center" class="mt-16">
                <v-col v-for="article of articles" :key="article.slug" cols="3">
                    <v-card elevation="6" class="px-5 py-5">
                        <v-card-title class="primary--text">{{article.title}}</v-card-title>
                        <v-card-title class="primary--text">{{article.createdAt}}</v-card-title>
                        <v-card-text>{{article.description}}</v-card-text>
                        <v-btn outlined color="primary" class="ml-3">
                            <NuxtLink :to="{name: 'blog-slug', params: {slug: article.slug}}" class="text-decoration-none" >Read more</NuxtLink>
                        </v-btn>
                    </v-card>
                </v-col>
            </v-row>
        </v-col>
    </v-row>
</template>

<script>
export default {
    async asyncData({$content, params}) {
        const articles = await $content('articles')
        .only(['title', 'description', 'img', 'slug', 'createdAt'])
        .sortBy('createdAt', 'asc')
        .fetch()
    
        return {articles}
    }
}
</script>