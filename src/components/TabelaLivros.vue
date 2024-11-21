<template>
    <h1 class="text-2xl text-center py-4">Tabela de Livros</h1>
    <!-- Inputs para tabela -->
    <div class="container mx-auto py-2 flex flex-col sm:flex-row sm:px-4 gap-2">
        <input type="text" v-model="titulo" placeholder="Digite o título"
            class="flex-grow bg-gray-200 rounded border border-gray-300 focus:outline-none shadow">
        <input type="text" v-model="autor" placeholder="Digite o autor"
            class="flex-grow bg-gray-200 rounded border border-gray-300 focus:outline-none shadow">
        <button @click="adicionarLivro" class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">Adicionar Livro</button>
    </div>
    <!-- Tabela de Livros -->
    <div class="container mx-auto">
        <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
            <table class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400">
                <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                    <tr>
                        <th scope="col" class="px-6 py-3">Título</th>
                        <th scope="col" class="px-6 py-3">Autor</th>
                        <th></th>
                    </tr>
                </thead>
                <tbody>
                    <tr class="odd:bg-white odd:dark:bg-gray-900 even:bg-gray-50 even:dark:bg-gray-800 border-b dark:border-gray-700"
                        v-for="livro in livros" :key="livro.titulo">
                        <td class="px-6 py-4">{{ livro.titulo }}</td>
                        <td class="px-6 py-4">{{ livro.autor }}</td>
                        <td class="px-6 py-4">
                            <button @click="removerLivro(livro)" class="px-4 py-2 bg-red-500 text-white rounded hover:bg-red-600">Remover</button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>

</template>

<script setup>
import { ref } from 'vue';

const titulo = ref('');
const autor = ref('');
const livros = ref([]);

const adicionarLivro = () => {
    if (titulo.value && autor.value) {
        livros.value.push({ titulo: titulo.value, autor: autor.value });
        titulo.value = '';
        autor.value = '';
    }
}

const removerLivro = (livro) => {
    livros.value = livros.value.filter(l => l !== livro);
}
</script>
