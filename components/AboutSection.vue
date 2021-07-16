<!-- Please remove this file from your project -->
<template>
    <div>
        <v-img v-if="$vuetify.theme.dark" src="wave.svg" height="300px" class="mt-16"></v-img>
        <v-img v-else-if="!$vuetify.theme.dark" src="wave-light.svg" height="300px" class="mt-16"></v-img>
        <v-container class="primary text--text" fluid>
            <v-row justify="center" class="pt-16 pb-16 pl-16 pr-16">
                <h2 class="pb-5">Hello. I'm Rodrigo. Nice to know you.</h2>
                <p class="pl-16 pr-16">
                    I have 2+ years of experience with programming in general, mostly with web stuff. I'm particulary fond of the back-end but I don't shy away from the front-end. My prefered language is JavaScript, but I also know Python, SQL, PHP and C++.
                    <br>I'm fond of challenges and new technologies, so I like to try new stuff all the time, which allows me to broad my view towards other languages, frameworks and libraries and most importantly learn to adapt to new tasks.
                    <br>I'm also experienced in using image editors like Photoshop and Ilustrator and UI/UX software like Adobe XD and Figma.
                    <br>As far has hobbies go I like to play videogames mostly rpgs and mmos like WoW and FFXIV and read japanese comic books whose number I read is too large for me to count or even estimate. I also like try new kinds of experience in my personal life, mostly food related, but I also love to travel and find more about other cultures and their yummy dishes. 
                </p>
            </v-row>
            <v-row class="primary mt-16 pt-16"></v-row>
        </v-container>
    </div>
</template>
