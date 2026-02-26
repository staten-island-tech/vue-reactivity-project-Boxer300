<template>
    <div>
        <h1>{{ cloth.name }}</h1>
        <h1>{{ cloth.price }}</h1>
    </div>
</template>

<script setup>
defineProps ({
    cloth:{
    type:Object,
    required:true
}
})
</script>

<style  scoped>

</style>