<template>
    <div>
        <v-img v-if="$vuetify.theme.dark" src="wave-down.svg" width="100%" height="300px"></v-img>
        <v-img v-else-if="!$vuetify.theme.dark" src="wave-down-light.svg" width="100%" height="300px"></v-img>
        <v-container class="mb-16 pb-16">
            <p class="text-center text-h4 pl-sm-0 pl-5 pr-sm-0 pr-5 font-weight-medium">So you wanna meet up? I'm honored, please express yourself has much has you can. I'm all ears.</p>
            <v-row justify="center" class="mt-16">
                <v-card elevation="6" height="650px" width="1000px">
                    <ValidationObserver ref="observer" v-slot="{handleSubmit}">
                        <v-form id="my-form" @submit.prevent="handleSubmit(onSubmit)">
                            <v-row justify="center" class="mt-10">
                                <v-col cols="5">
                                    <ValidationProvider v-slot="{ errors, valid }" name="Name" rules="required|min:5|max:15|alpha_spaces">
                                        <v-text-field v-model="name" name="name"  :error-messages="errors" :success="valid" type="text" label="Name" counter="15" outlined></v-text-field>
                                    </ValidationProvider>
                                </v-col>
                                <v-col cols="5">
                                    <ValidationProvider v-slot="{errors, valid}" name="Email" rules="required|email|max:30">
                                        <v-text-field v-model="email" name="email" :error-messages="errors" :success="valid" type="text" label="Email" counter="30" outlined></v-text-field>
                                    </ValidationProvider>
                                </v-col>
                            </v-row>
                            <v-row justify="center">
                                <v-col cols="10">
                                    <ValidationProvider v-slot="{errors, valid}" name="Message" rules="required|min:20|max:300">
                                        <v-textarea v-model="message" name="message" :error-messages="errors" :success="valid" label="Message" counter="300" no-resize height="300px" outlined clearable clear-icon="mdi-close"></v-textarea>
                                    </ValidationProvider>
                                </v-col>
                            </v-row>
                            <v-row justify="center" class="mt-6">
                                <v-btn type="submit" outlined>Submit</v-btn>
                            </v-row>
                            <v-row justify="center" class="mt-6">
                                <v-alert v-if="isValid === true" type="success" dismissible outlined>Form submitted</v-alert>
                            </v-row>
                        </v-form>
                    </ValidationObserver>
                </v-card>
            </v-row>
        </v-container>
    </div>
</template>

<script>
    import {extend, ValidationProvider, ValidationObserver} from 'vee-validate'
    import {alpha_spaces, email, required} from 'vee-validate/dist/rules'
    import emailjs from 'emailjs-com';

    
    export default {
        components: {
            ValidationProvider,
            ValidationObserver
        },
        data: () => ({
            name: '',
            message: '',
            email: '',
            isValid: false
        }),
        methods: {
            onSubmit() {
                this.$refs.observer.validate().then(success => {
                    if(success) {
                        this.sendEmail();
                    }
                });
            },
            sendEmail() {
                try {
                    emailjs.sendForm(process.env.SERVICE_ID, process.env.TEMPLATE_ID, '#my-form',
                    process.env.USER_ID, {
                        name: this.name,
                        email: this.email,
                        message: this.message
                    })
                } catch(error) {
                    console.log({error})
                }
                this.name = this.email = this.message = '';
                this.isValid = true;
            },
        },
    }
    
    extend('max', {
        validate(value, args) {
            return value.length <= args.length;
        },
        params: ['length'],
        message: '{_field_} cannot exceed {length} characters'
    });
    extend('min', {
        validate(value, args) {
            return value.length >= args.length;
        },
        params: ['length'],
        message: '{_field_} needs to be greater than {length} characters'
    });
    extend('required', {
        ...required,
        message: '{_field_} is required'
    })
    extend('email', {
        ...email,
        message: 'Invalid email format'
    })
    extend('alpha_spaces', {
        ...alpha_spaces,
        message: '{_field_} only alphabetic characters are allowed'
    })
</script>