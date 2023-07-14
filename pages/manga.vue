<template>
  <div class="text-center mt-8">
    <h2 class="text-3xl font-bold">{{ manga.title }}</h2>
    <p class="text-xl mt-4">{{ manga.genre }}</p>
    <p class="mt-4">{{ manga.description }}</p>
    <div class="mt-8">
      <a :href="manga.downloadLink" class="bg-primary hover:bg-purple-700 text-white py-2 px-4 rounded inline-block" title="Скачать мангу">
        <span v-if="loading">
          Загрузка...
        </span>
        <span v-else>
          Скачать мангу
        </span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      manga: {
        title: 'Тетрадь смерти',
        genre: 'Детектив, фэнтези',
        description: 'Тетрадь, в которой записываются имена людей, умерших от её владельца. Какие будут последствия?',
        downloadLink: 'https://www.youtube.com/watch?v=dQw4w9WgXcQ' // Замените путь на фактический путь для скачивания манги
      },
      loading: false
    }
  }
}
</script>

<style scoped>
.text-center {
  text-align: center;
}

.text-3xl {
  font-size: 2rem;
}

.font-bold {
  font-weight: bold;
}

.mt-8 {
  margin-top: 2rem;
}

.text-xl {
  font-size: 1.5rem;
}

.mt-4 {
  margin-top: 1rem;
}

.bg-primary {
  background-color: #4f46e5;
}

.hover\:bg-purple-700:hover {
  background-color: #6b46e5;
}

.text-white {
  color: #ffffff;
}

.py-2 {
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
}

.px-4 {
  padding-left: 1rem;
  padding-right: 1rem;
}

.rounded {
  border-radius: 0.25rem;
}

a {
  text-decoration: none;
}
</style>
