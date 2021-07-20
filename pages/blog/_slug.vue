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
    <div>
        <v-img v-if="$vuetify.theme.dark" src="/wave-down.svg" width="100%" height="300px"></v-img>
        <v-img v-else-if="!$vuetify.theme.dark" src="/wave-down-light.svg" width="100%" height="300px"></v-img>
        <article class="mt-16 text--text">
            <v-row justify="center" class="mt-16">
                <v-col cols="12" sm="10">
                    <v-sheet elevation="6" class="px-10 py-10">
                        <v-img :src="article.img" :alt="article.alt" width="100%" height="350px" class="mb-16"></v-img>
                        <p class="text-h7 font-weight-light grey--text">{{formatDate(article.updatedAt)}}</p>
                        <h1 class="text-h2 font-weight-medium primary--text text-break">{{article.title}}</h1>       
                        <nuxt-content :document="article" class="mt-16 text-break" />
                        <prev-next :prev="prev" :next="next" class="mt-8" />
                    </v-sheet>
                </v-col>
            </v-row>
        </article>
        <v-img v-if="$vuetify.theme.dark" src="/wave.svg" height="300px" class="mt-16"></v-img>
        <v-img v-else-if="!$vuetify.theme.dark" src="/wave-light.svg" height="300px" class="mt-16"></v-img>
        <v-container class="primary" fluid>
            <v-row justify="center">
                <v-col cols="10" sm="6" class="text-center pl-16 pr-16 text--text">
                    <p class="text-h4 font-weight-medium ">Like what you see? <br>Wanna have a chat? <br>I'll buy the coffee.</p>
                    <p class="text-h6 font-weight-light ">Have a job you would like to offer?</p>
                    <v-btn color="white" outlined elevation="1" class="mb-16">
                        <nuxt-link to="/contact" class="text-decoration-none text--text">Hire me</nuxt-link>
                    </v-btn> 
                </v-col>
                <v-col cols="12" sm="6">
                    <v-row justify="center">
                        <v-icon class="ml-sm-16 pb-3 pt-n3 pr-2" color="text" large>mdi-email</v-icon>
                        <p class="text-h6 text--text">cielos20@hotmail.com</p>
                    </v-row>
                    <v-row justify="center" class="pb-5 pb-sm-0">
                        <v-icon class="ml-sm-n16 pb-3 pt-n3 pr-2" color="text" large>mdi-github</v-icon>
                        <p class="text-h6 text--text">cielos20</p>
                    </v-row>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>