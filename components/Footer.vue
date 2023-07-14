<template>
  <header class="bg-primary text-white py-4 px-6 w-full">
    <h1 class="text-2xl font-bold text-center"><slot></slot></h1>
  </header>
</template>

<style scoped>
.bg-primary {
  background-color: #4f46e5;
}

.text-white {
  color: #ffffff;
}
</style>