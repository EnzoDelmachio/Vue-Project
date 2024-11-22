<template>
    <section class="bg-gray-100 flex h-screen items-center">
        <div class="container mx-auto py-16 px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 items-center gap-8">
                <div class="max-w-lg">
                    <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">Sobre Nós</h2>
                    <div v-if="indice === 0">
                        <p class="mt-4 text-gray-600 text-lg">
                            Nome: Enzo Delmachio <br>
                            Curso: Engenharia de Software E4-2022 <br>
                            Empresa: UniFil <br>
                            Cargo: Desenvolvedor <br>
                            Framework: Vue.js
                        </p>
                    </div>
                    <div v-else>
                        <p class="mt-4 text-gray-600 text-lg">
                            Nome: Gabriel Dante Dutra Gomes<br>
                            Curso: Engenharia de Software E3-2024 <br>
                            Empresa: UniFil <br>
                            Cargo: Desenvolvedor <br>
                            Framework: Vue.js
                        </p>
                    </div>
                    <div class="mt-8">
                        <a href="#" class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600"
                            @click="indice = indice === 0 ? 1 : 0">Ver mais
                            <span class="ml-2">&#8594;</span></a>
                    </div>
                    <div class="mt-8">
                        <RouterLink to="/livros" class="text-blue-500 hover:text-blue-600 font-medium">
                            <span class="ml-2">&#8592;</span>
                            Livros
                        </RouterLink>
                    </div>
                </div>
                <div class="mt-12 md:mt-0">
                    <transition name="fade" mode="out-in">
                        <div class="componente" v-if="indice === 0">
                            <img src="@/assets/IMG_41502.png" alt="About Us Image"
                                class="object-cover rounded-lg shadow-md">
                        </div>
                        <div v-else>
                            <img src="@/assets/Wp-Image.jpg" alt="About Us Image"
                                class="object-cover rounded-lg shadow-md">
                        </div>
                    </transition>

                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const indice = ref(0);

</script>

<style>

.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s ease-out;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>