<template>
    <div>
        name: <input v-model="name" placeholder="Name" />
    </div>
</template>

<script setup lang="ts">
    const name = ref('')

    await useLoadShipment()
</script>
