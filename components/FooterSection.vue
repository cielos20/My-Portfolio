<template>
    <div>
        <v-img v-if="$vuetify.theme.dark" src="wave.svg" height="300px" class="mt-16"></v-img>
        <v-img v-else-if="!$vuetify.theme.dark" src="wave-light.svg" height="300px" class="mt-16"></v-img>
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
                    <v-row justify="center" class="pb-5 pb-sm-0">
                        <p class="text-h6 text--text">Thank you, Storyset for the wonderful art.<br>Click the <a href="https://storyset.com/" class="text--text">link</a> to see more awesome ilustrations.</p>
                    </v-row>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>