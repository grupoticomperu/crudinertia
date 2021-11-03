<template>
    <app-layout title="Dashboard">
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Nuevo Usuario
            </h2>
        </template>
        

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-xl sm:rounded-lg">
                  <div class="p-6 bg-white border-b border-gray-200 sm:px-20">  

                   <form @submit.prevent="submit">
                       <div class="mt-4">
                            <jet-label value="Nombre:"/>
                            <input-error :message="errors.name" />
                            <jet-input class="block w-full mt-1" type="text" v-model="form.name" /> 
                       </div>

                       <div class="mt-4">
                            <jet-label value="Email:"/>
                            <input-error :message="errors.email" />
                            <jet-input class="block w-full mt-1" type="text" v-model="form.email" /> 
                       </div>

                       <div class="mt-4">
                            <jet-label value="Password:"/>
                            <input-error :message="errors.password" />
                            <jet-input class="block w-full mt-1" type="password" v-model="form.password" /> 
                       </div>
                        
                       <div class="mt-4">
                             <jet-button type="submit">Enviar</jet-button>
                       </div>

                   </form> 

                   </div>  
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import { defineComponent } from 'vue'
    import AppLayout from '@/Layouts/AppLayout.vue'
    import { Inertia } from '@inertiajs/inertia'
    import InputError from "@/Jetstream/InputError"
    import JetInput from "@/Jetstream/Input"
    import JetLabel from "@/Jetstream/Label"
    import JetButton from '@/Jetstream/Button.vue'
    export default {
        props: ["errors"],
        data(){
            return{
                form: {
                    name:"",
                    email:"",
                    password:""
                }
            }
        },
        components: {
            AppLayout,
            InputError,
            JetInput,
            JetLabel,
            JetButton
        },
        methods: {
            submit(){
                Inertia.post(route('user.store'), this.form)

            },//fin del submit
        },
    };
</script>
