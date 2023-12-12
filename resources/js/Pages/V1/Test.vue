<script setup>
import { Head } from '@inertiajs/vue3'
import { Link } from '@inertiajs/vue3'

defineProps({
   user : Object
 })
</script>

<template>
    <Head>
        <title>Test Title  </title>
        <meta name="description" content="Your page description">
    </Head>
<body>


<div class="relative overflow-x-auto">
    <button @click="toggleDark()">
        <i inline-block align-middle i="dark:carbon-moon carbon-sun" />

        <span class="ml-2">{{ isDark ? 'Dark' : 'Light' }}</span>
    </button>
    <table class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400">
        <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
        <tr>
            <th scope="col" class="px-6 py-3">
                ID
            </th>
            <th scope="col" class="px-6 py-3">
               Name
            </th>
            <th scope="col" class="px-6 py-3">
                Email
            </th>
            <th scope="col" class="px-6 py-3">
                Created At
            </th>
        </tr>
        </thead>
        <tbody v-for="val in user" :key="val.id">
        <tr class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
            <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                {{ val.id   }}
            </th>
            <td class="px-6 py-4">
                {{ val.name  }}
            </td>
            <td class="px-6 py-4">
                {{ val.email }}
            </td>
            <td class="px-6 py-4">
<!--                {{ user.createAt }}-->
            23/11/11
            </td>
        </tr>

        </tbody>
    </table>
</div>

<Link href="/"> Home Page</Link>

<br>
<Link href="/"  class="bg-blue-400 hover:bg-blue-700 text-white font-bold rounded px-4 py-2" as="button" type="button">Link Button</Link>
<br>


<center>
    <input v-model="query" type="text" />

    <Link href="/" :data="{ query }" preserve-state>Search</Link>
</center>
</body>


</template>

<style scoped>

</style>
