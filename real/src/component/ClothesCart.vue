<template>
    <div>
<!--         <h2>{{ cloth.name }}</h2>
        <h2>{{ cloth.price }}</h2> 
        <button>Remove</button> -->
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