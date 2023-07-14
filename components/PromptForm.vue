<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold mb-4">Генератор манги</h2>
    <form @submit.prevent="generateManga">
      <div class="flex items-center">
        <label for="prompt" class="mr-2">Промпт:</label>
        <input type="text" v-model="prompt" class="border border-gray-300 px-2 py-1 rounded" />
      </div>
      <div class="flex items-center mt-2">
        <label for="genre" class="mr-2">Жанр:</label>
        <select v-model="genre" class="border border-gray-300 px-2 py-1 rounded">
          <option value="action">Seinen</option>
          <!-- <option value="romance">Романтика</option>
          <option value="comedy">Комедия</option>
          <option value="fantasy">Фэнтези</option> -->
        </select>
      </div>
      <button type="submit" class="mt-4 bg-primary hover:bg-purple-700 text-white py-2 px-4 rounded">
        Сгенерировать
      </button>
    </form>
    <div v-if="generatedManga" class="mt-8">
      <h3 class="text-lg font-bold mt-4">Сгенерированная манга:</h3>
      <div class="border border-gray-300 rounded p-4">
        <p v-for="(page, index) in generatedManga" :key="index">{{ page }}</p>
      </div>
    </div>
  </div>
</template>


<script>
export default {
data() {
  return {
    prompt: '',
    genre: '',
    generatedManga: null
  }
},
methods: {
  generateManga() {
    // В этом методе вы можете вызвать ваш API для генерации манги с использованием переданных промптов и жанра.
    // Здесь мы просто используем моковые данные.
    const mockManga = [
      `Title: "The Demon Within: A Journey of Self-Discovery"
Genre: Seinen

Chapter Titles:

    "The Darkening of the Soul: An Inner Battle"

Main Characters:

    Kazuki: The main protagonist of the manga, Kazuki is a 15-year-old high schooler who is struggling with his identity and his place in the world. He is introverted and has difficulty fitting in, but he is determined to find his true self. Kazuki is depicted as a kind and gentle person, but he must confront his inner darkness during his journey.
    Hikari: A mysterious girl who Kazuki meets during his journey. She appears in his dreams, offering encouragement and advice. Hikari helps Kazuki explore his inner demons and guides him on his path to self-discovery.
    Yukio: An old friend of Kazuki's who provides support and guidance. Yukio is an experienced martial artist with insight into the spiritual world.
    Takashi: A classmate of Kazuki's who is also struggling with his own identity. He offers a unique perspective on life and helps Kazuki understand his own struggles.
    Fujiwara: The main antagonist of the series, Fujiwara is a powerful demon terrorizing the area. He aims to prevent Kazuki from achieving his goal of self-discovery.

Funservice Characters:
The funservice characters are a group of mischievous and friendly spirits that inhabit the world of the manga. They are anthropomorphic animals such as cats, dogs, and rabbits. These characters play pranks and provide comic relief throughout the story. They have a special bond with the protagonist and assist her in her adventures, using their magical powers to help her overcome challenges.

Detailed Character Descriptions:

    Kazuki: A 15-year-old high schooler with pale skin, short black hair, and brown eyes. He often wears a white school uniform, exuding an air of sadness and melancholy.
    Hikari: With long wavy blonde hair and bright blue eyes, Hikari typically wears a white kimono with a red obi. She possesses a mysterious and ethereal aura.
    Yukio: Yukio has a muscular build, short black hair, and wears a traditional martial arts uniform. He provides wisdom and guidance to Kazuki.
    Takashi: Takashi has short brown hair and is usually seen in a school uniform. He occasionally experiences jealousy towards Kazuki's strength but remains a supportive friend.
    Fujiwara: A tall and imposing demon with long black hair, pale skin, and dark eyes. Fujiwara serves as the main antagonist, determined to hinder Kazuki's goals.

Manga Chapter Story:
"The Demon Within: A Journey of Self-Discovery" follows Kazuki, a 15-year-old high school student searching for his identity and purpose. With the assistance of his old friend Yukio, the mysterious Hikari, and classmate Takashi, Kazuki embarks on a transformative journey. Throughout the story, Kazuki confronts his inner demons and struggles with his sense of self. The funservice characters, mischievous and friendly spirits, accompany him, offering assistance, guidance, and comic relief. However, Kazuki must also face the formidable demon, Fujiwara, who seeks to prevent his self-discovery. Will Kazuki overcome the obstacles and find his true self? Join him in "The Demon Within: A Journey of Self-Discovery" to uncover the answer.`
    ];
    this.generatedManga = mockManga;

    // Имитация задержки перед отображением сгенерированной манги
    setTimeout(() => {
      this.$emit('manga-generated');
    }, 2000);
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
