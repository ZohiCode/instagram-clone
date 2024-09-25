<template>
  <div class="flex items-center bg-white py-4 px-1 rounded-lg ">
    <img :src="message.image" alt="Profile Image" class="w-16 h-16 rounded-full mr-4" />
    <div>
      <p class="text-sm font-semibold">{{ message.from }}</p>
      <p class="text-sm text-gray-500">{{ message.content }} </p>

      <p class="text-xs text-gray-500 mt-1">
        {{ message.timeAgo }}
      </p>

    </div>
    <button class="ml-auto me-4 text-blue-500 text-sm font-semibold hover:text-blue-700">
      Follow
    </button>
  </div>
</template>

<script>
export default {
  props: {
    message: Object,
  },
};
</script>

<style scoped>
/* Custom styles if needed */
</style>
