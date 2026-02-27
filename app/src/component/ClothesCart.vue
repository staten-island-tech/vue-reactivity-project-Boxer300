<template>
    <div>
        <h1>{{ cloth.name }}</h1>
        <h2>{{ cloth.price }}</h2>
    </div>
    <slot></slot>
</template>

<script setup>
defineProps ({
    cloth:{
    type: Object,
    required: true,
}
})
</script>

<style  scoped>

</style>