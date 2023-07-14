<template>
  <div>
    <PromptForm v-on:manga-generated="showManga" />
    <div v-if="mangaGenerated">
      <nuxt-child />
    </div>
  </div>
</template>

<script>
import PromptForm from '@/components/PromptForm.vue';

export default {
  components: {
    PromptForm
  },
  data() {
    return {
      mangaGenerated: false
    }
  },
  methods: {
    showManga() {
      this.mangaGenerated = true;
      this.$router.push('/manga');
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

.mt-8 {
  margin-top: 2rem;
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

