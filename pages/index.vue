<template>
  <div id="body" :style="`background: radial-gradient(circle at ${x - 10}px ${y - 120}px, white, #eeffbb 100%);`">
    index
    <counter>aaaa</counter>
    {{ x }}
    {{ y }}

    <ul>
      <li v-for="user in users" :key="user.id">{{ user.name }}</li>
    </ul>

    <ul>
      <li v-for="user in users2" :key="user.id">{{ user.name }}</li>
    </ul>

    <ul>
      {{ user }}
    </ul>

    <ul>
      <li> {{ weather.weather[0].description }}</li>
      <li>{{ weather.main.temp }}</li>
    </ul>
  </div>
  <div>

  </div>
</template>

<script setup>

const { x, y } = useMouse();
const users = ref([])

onMounted(() => {
  fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())
    .then(data => users.value = data)
})

const { data: users2 } = await useAsyncData('users2', () => $fetch('https://jsonplaceholder.typicode.com/users'))

const { data: weather } = await useFetch(`/api/weather`)
</script>

<style>
#body {
  width: 1000px;
  height: 1000px;
}
</style>
