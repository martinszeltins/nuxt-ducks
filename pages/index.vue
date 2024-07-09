<template>
    <div>
        <Shipment />

        <div><NuxtLink to="/">HOME</NuxtLink></div>
        <div><NuxtLink to="/?name=roro">/?name=roro</NuxtLink></div>
        <div><NuxtLink to="/about">About</NuxtLink></div>

        <ul>
            <li>Enter a name in the input field above</li>
            <li>Click on the ?name=roro link</li>
            <li>Click on the HOME link</li>
            <li>The page should be re-rendered and reset but it's not happening. The input should be cleared.</li>
        </ul>
    </div>
</template>

<script setup lang="ts">
    const route = useRoute()

    onBeforeRouteUpdate(to => {
        // Refresh the page (not hard refresh)!
        if (to.fullPath === '/') {
            route.meta.pageKey = 'test'

            document.querySelector('#logs')!.textContent = document.querySelector('#logs')!.textContent + 'Changing page key, it should re-render the page and clear all data...'
        }
    })

    definePageMeta({ key: (route) => route.meta.pageKey })
</script>
