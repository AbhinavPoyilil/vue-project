<script setup>
const { total } = defineProps(["total"])
</script>
<template>
    <h1> my shopping list </h1>
     <h2> Total : {{ total }} </h2>
</template>