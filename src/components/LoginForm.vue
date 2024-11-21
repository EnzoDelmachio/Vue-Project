<template>
    <div class="flex h-screen items-center justify-center bg-gray-100">
        <div class="bg-white p-8 rounded shadow-md">
            <h2 class="text-2xl font-bold mb-6">Login</h2>
            <form>
                <div class="mb-4">
                    <label class="block text-gray-700 text-sm font-bold mb-2" for="email">
                        Email
                    </label>
                    <input type="email" id="email"
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Seu email">
                </div>
                <div class="mb-6">
                    <label class="block text-gray-700 text-sm font-bold mb-2" for="password">
                        Senha
                    </label>
                    <input type="password" id="password"
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Sua senha">
                </div>
                <div class="flex items-center justify-between">
                    <RouterLink to="/livros"
                        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline">
                        Entrar
                    </RouterLink>
                    <a href="#" class="inline-block align-baseline text-sm text-blue-500 hover:text-blue-800">
                        Esqueceu a senha?
                    </a>
                </div>
            </form>
        </div>
    </div>
</template>
