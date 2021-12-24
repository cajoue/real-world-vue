<template>
    <p>{{ total }}</p>
    <button @click="total += 1">Increment</button>
</template>

<script>
export default {
    data() {
        return {
            total: 0
        }
    },
}
</script>

<style>
p {
    font-size: 16px;
}
</style>