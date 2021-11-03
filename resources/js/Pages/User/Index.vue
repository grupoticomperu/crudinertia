<template>
    <app-layout title="Dashboard">
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Users
            </h2>
        </template>

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-xl sm:rounded-lg">

           

                   <Link :href="route('user.create')">
                   
                        <button
                            data-modal-toggle="example"
                            data-modal-action="open"
                            class="w-32 p-2 m-2 font-semibold text-white transition-all duration-300 bg-red-600 rounded-full shadow-lg hover:bg-red-700 focus:outline-none focus:ring hover:shadow-none"
                        >
                            Crear Usuario 
                        </button>
                   </Link>
   
                    <table class="w-full table-auto">
                     <thead>
                        <tr>
                            <th class="p-3">ID</th>
                            <th class="p-3">Nombress</th>
                            <th class="p-3">Email</th>
                            <th class="p-3">Acciones</th>
                        </tr>
                     </thead>
                     <tbody>
                      <tr v-for="u in users" :key="u.id">
                        <td class="p-3 border">{{u.id}}</td>
                        <td class="p-3 border">{{u.name}}</td>
                        <td class="p-3 border">{{u.email}}</td>
                        <td class="p-3 border">
                            <Link :href="route('user.show', { customer: u })">
                                ver 
                            </Link>
                            
                            <Link :href="route('user.edit', { customer: u })">
                                Editar 
                            </Link>
                            <Link method="DELETE" :href="route('user.destroy', { customer: u })">
                                Eliminar
                            </Link>
                        </td>
                      </tr>

                     </tbody>
                    </table>

                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import { Head, Link } from '@inertiajs/inertia-vue3'
    import { defineComponent } from 'vue'
    import AppLayout from '@/Layouts/AppLayout.vue'
    
    
    export default defineComponent({
        props:['users'],
        components: {
            AppLayout,
            Head,
            Link,
        },
    })
</script>
