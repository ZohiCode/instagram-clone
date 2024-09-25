<template>
  <div class="relative bg-white rounded-lg shadow-lg overflow-hidden group transition-shadow duration-300">
    <img :src="post.image" alt="Post image" class="w-full h-auto object-cover" />

    <!-- Mask & Interaction Icons -->
    <div
      class="absolute inset-0 bg-black bg-opacity-50 flex flex-col items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300 ease-in-out	">
      <div class="flex space-x-4">
        <span class="flex items-center text-white">
          <i class="fas fa-heart mr-1" @click="toggleLike" :class="{ 'text-red-500': liked }"></i>
          <span>{{ post.likes }}</span>
        </span>
        <span class="flex items-center text-white">
          <i class="fas fa-comment mr-1"></i>
          <span>{{ post.comments }}</span>
        </span>
        <span class="flex items-center text-white">
          <i class="fas fa-share mr-1"></i>
          <span>{{ post.shares }}</span>
        </span>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      liked: false,
    };
  },
  methods: {
    toggleLike() {
      this.liked = !this.liked;
      this.post.likes += this.liked ? 1 : -1;

    },
  },
  props: {
    post: {
      type: Object,
      required: true,
    },
  },

};
</script>

<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css');

/* Gerekirse ek stil ayarları buraya ekleyebilirsiniz */
</style>
