<template>
    <app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Users
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <div>
                        <div class="p-6 sm:px-20 bg-white border-gray-200">
                            <div class="mt-2 text-xl">
                                User Details
                            </div>
                            <div class="overflow-x-auto">
                                <div class="bg-white my-6">
                                    <div class="flex flex-col space-y-4">
                                        <div class="flex flex-col items-center md:items-start">
                                            <h2 class="text-xl font-medium">{{ user.name }}</h2>
                                            <p class="text-base font-medium text-gray-400">{{ user.email }}</p>
                                        </div>
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

    export default {
        components: {
            AppLayout
        },
        props: ['user']
    }
</script>
