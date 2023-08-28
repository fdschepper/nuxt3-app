<template>
    <div>
        {{ count }} {{ extra }}
        <button @click="increment">+</button>
        <button @click="decrement">-</button>
    </div>
</template>

<script setup>
const count = ref(0);

const extra = computed(() => count.value ** count.value)

function increment() {
    count.value++;
}

function decrement() {
    count.value--;
}

</script>