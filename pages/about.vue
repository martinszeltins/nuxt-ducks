<template>
    <div>
        About

        <NuxtLink to="/">Home</NuxtLink>
    </div>
</template>

<script setup lang="ts">
    const route = useRoute()

    definePageMeta({ key: (route) => route.meta.pageKey })

    onBeforeRouteUpdate(() => {
        route.meta.pageKey = 'test'
    })
</script>
