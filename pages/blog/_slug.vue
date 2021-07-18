<script>
export default {
    async asyncData({$content, params}) {
        const article = await $content('articles', params.slug).fetch()
        const [prev, next] = await $content('articles')
        .only(['title', 'slug'])
        .sortBy('createdAt', 'asc')
        .surround(params.slug)
        .fetch()

        return {
            article,
            prev,
            next
        }
    },
    methods: {
        formatDate(date) {
            const options = {year: 'numeric', month: 'long', day: 'numeric'}
            return new Date(date).toLocaleDateString('en', options)
        }
    }
}
</script>

<template>
    <article class="mt-16 mb-10 text--text">
        <v-row justify="center" class="mt-16">
            <v-col cols="7">
                <v-sheet elevation="6" class="px-10 py-10">
                    <v-img :src="article.img" :alt="article.alt" width="100%" height="350px" class="mb-16"></v-img>
                    <p class="text-h7 font-weight-light grey--text">{{formatDate(article.updatedAt)}}</p>
                    <h1 class="text-h2 font-weight-medium primary--text">{{article.title}}</h1>       
                    <nuxt-content :document="article" class="mt-16" />
                    <prev-next :prev="prev" :next="next" />
                </v-sheet>
            </v-col>
        </v-row>
    </article>
</template>