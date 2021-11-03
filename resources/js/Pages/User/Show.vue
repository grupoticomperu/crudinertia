<template>
    <app-layout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Users
            </h2>
        </template>

        

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                                               
                       <label>{{ user.name }}</label>
                       <label>{{ user.email }}</label>
            
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    

    import { defineComponent } from 'vue'
    import AppLayout from '@/Layouts/AppLayout.vue'
   // import JetLabel from '@Jetstream/Label'

    export default {
        props: ["user"],

        components: {
            AppLayout
        },
      
    };
</script>
