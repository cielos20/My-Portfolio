<template>
<!-- Need to figure out how to put this workin -->
<!-- Style this better -->
    <div>
        <p>I'm the post section</p>
        <v-row justify="center" class="mt-16">
            <v-col v-for="article in articles" :key="article.slug">
                <v-card elevation="6">
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
     async asyncData({$content}) {
        const articles = await $content('articles')
        .only(['title', 'description', 'slug', 'createdAt'])
        .sortBy('createdAt', 'asc')
        .limit(3)
        .fetch()
        
        return {articles}
    },
    methods: {
        formatDate(date) {
            const options = {year: 'numeric', month: 'long', day: 'numeric'}
            return new Date(date).toLocaleDateString('en', options)
        }
    }
}
</script>
