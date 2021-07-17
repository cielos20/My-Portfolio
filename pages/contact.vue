<template>
    <v-container class="mt-16 pt-16 mb-16 pb-16">
        <p class="text-center text-h4 pl-sm-0 pl-5 pr-sm-0 pr-5 font-weight-medium">So you wanna meet up? I'm honored, please express yourself has much has you can. I'm all ears.</p>
        <v-row justify="center" class="mt-16">
            <v-card elevation="6" height="650px" width="1000px">
                <ValidationObserver ref="observer">
                    <v-form @submit.prevent="submit">
                        <v-row justify="center" class="mt-10">
                            <v-col cols="5">
                                <ValidationProvider v-slot="{ errors, valid }" name="Name" rules="required|min:5|max:15">
                                    <v-text-field v-model="name" :error-messages="errors" :success="valid" type="text" label="Name" counter="15" outlined></v-text-field>
                                </ValidationProvider>
                            </v-col>
                            <v-col cols="5">
                                <ValidationProvider v-slot="{errors, valid}" name="Email" rules="required|email">
                                    <v-text-field v-model="email" :error-messages="errors" :success="valid" type="text" label="Email" counter="15" outlined></v-text-field>
                                </ValidationProvider>
                            </v-col>
                        </v-row>
                        <v-row justify="center">
                            <v-col cols="10">
                                <ValidationProvider v-slot="{errors, valid}" name="Message" rules="required|min:20|max:300">
                                    <v-textarea v-model="message" :error-messages="errors" :success="valid" label="Message" counter="300" no-resize height="300px" outlined clearable clear-icon="mdi-close"></v-textarea>
                                </ValidationProvider>
                            </v-col>
                        </v-row>
                        <v-row justify="center" class="mt-6">
                            <v-btn type="submit" outlined>Submit</v-btn>
                        </v-row>
                        <v-row justify="center" class="mt-6">
                            <!-- Need to figure out why it only happens once -->
                            <v-alert v-if="isValid === false" type="error" dismissible outlined>Invalid Form</v-alert>
                            <v-alert v-if="isValid === true" type="success" dismissible outlined>Form submitted</v-alert>
                        </v-row>
                    </v-form>
                </ValidationObserver>
            </v-card>
        </v-row>
    </v-container>
</template>

<script>
    import {extend, ValidationProvider, ValidationObserver} from 'vee-validate'
    import {email, required} from 'vee-validate/dist/rules'

    
    export default {
        components: {
            ValidationProvider,
            ValidationObserver
        },
        data: () => ({
            name: '',
            message: '',
            email: '',
            isValid: ''
        }),
        methods: {
            submit() {
                this.$refs.observer.validate().then(success => {
                    if(!success) {
                        this.isValid = false;
                    }
                    else {
                        this.isValid = true;
                        this.name = this.email = this.message = '';
                        this.$nextTick(() => {
                            this.$refs.observer.reset();
                        });
                    }
                })
            }
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
        message: '{_field_} is invalid'
    })
    extend('email', {
        ...email,
        message: '{_field_} is invalid'
    })
</script>