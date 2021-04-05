<template>
    <app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <div>
                        <div class="p-6 sm:px-20 bg-white border-gray-200">
                            <div class="mt-2 text-xl">
                                Edit user
                            </div>
                            <div class="overflow-x-auto">
                                <div class="bg-white my-6">
                                    <div>
                                        <jet-validation-errors class="mb-4" />
                                        <form @submit.prevent="submit" >
                                            <div>
                                                <jet-label for="name" value="Name" />
                                                <jet-input id="name" type="text" class="mt-1 block w-full" v-model="form.name" required autofocus autocomplete="name" />
                                            </div>

                                            <div class="mt-4">
                                                <jet-label for="email" value="Email" />
                                                <jet-input id="email" type="email" class="mt-1 block w-full" v-model="form.email" required />
                                            </div>

                                            <div class="flex justify-end mt-4">
                                                <jet-button class="ml-4" :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                                                    Update
                                                </jet-button>
                                            </div>
                                        </form>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout'
    import JetAuthenticationCard from '@/Jetstream/AuthenticationCard'
    import JetAuthenticationCardLogo from '@/Jetstream/AuthenticationCardLogo'
    import JetButton from '@/Jetstream/Button'
    import JetInput from '@/Jetstream/Input'
    import JetCheckbox from "@/Jetstream/Checkbox";
    import JetLabel from '@/Jetstream/Label'
    import JetValidationErrors from '@/Jetstream/ValidationErrors'

    export default {
        components: {
            AppLayout,
            JetAuthenticationCard,
            JetAuthenticationCardLogo,
            JetButton,
            JetInput,
            JetCheckbox,
            JetLabel,
            JetValidationErrors
        },

        data() {
            return {
                form: {
                    name: '',
                    email: '',
                }
            }
        },

        created() {
            this.form = this.data;
        },

        methods: {
            submit() {
                this.$inertia.put(this.route('users.update', this.data.id), this.form)
            }
        },

        props: ["data"],
    }
</script>
