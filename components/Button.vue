<template>
  <a :href="href" class="bg-primary hover:bg-purple-700 text-white py-2 px-4 rounded">
    <slot></slot>
  </a>
</template>

<script>
export default {
  props: {
    href: {
      type: String,
      default: '#'
    }
  }
}
</script>
