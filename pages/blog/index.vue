<template>
    <div>
    <v-img v-if="$vuetify.theme.dark" src="wave-down.svg" width="100%" height="300px"></v-img>
    <v-img v-else-if="!$vuetify.theme.dark" src="wave-down-light.svg" width="100%" height="300px"></v-img>
    <v-row class="mt-n10">
        <v-col>
            <v-row justify="center">
                <v-col cols="8" sm="7">
                    <h1 class="text-left text-h3 font-weight-medium">The Blog</h1>
                </v-col>
            </v-row>
            <!-- Make some tabs to filter the content maybe or some tags -->
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
        </v-col>
    </v-row>
    <FooterSection />
    </div>
</template>

<script>
export default {
    async asyncData({$content, params}) {
        const articles = await $content('articles')
        .only(['title', 'description', 'img', 'slug', 'createdAt'])
        .sortBy('createdAt', 'asc')
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