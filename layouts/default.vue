<template>
  <div>
    <Navbar />
    <NuxtPage class="container mx-auto pt-8" />
  </div>
</template>

<script >
import Navbar from '~/components/Navbar.vue';

export default {
  components: {
    Navbar,
  },
};
</script>
