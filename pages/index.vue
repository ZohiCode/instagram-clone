<template>
  <div class="h-screen">
    <!-- Header Section -->

    <!-- Main Content Section -->
    <main class="pt-5 max-w-4xl mx-auto">
      <!-- Stories Section -->
      <div class="flex space-x-2 py-4 overflow-x-scroll scrollbar-hide">
        <div v-for="story in FollowedStories" :key="story.id" class="w-20 flex flex-col items-center">
          <img :src="story.image" alt="Story Image" class="w-16 h-16 rounded-full border-2 border-pink-500" />

          <!-- Metni sabit genişlikte tutup ortalayarak ve dilimleyerek düzenliyoruz -->
          <span class="text-sm mt-2 w-40 text-center truncate" style="min-width: 10ch;">
            {{ story.name.length > 10 ? story.name.slice(0, 10) + '...' : story.name }}
          </span>
        </div>
      </div>


      <!-- Posts Section -->
      <div class="mt-6 space-y-6">
        <Post v-for="post in FollowedPosts" :key="post.id" :post="post" />
      </div>
    </main>
  </div>
</template>

<script>
import PostCard from '~/components/Post.vue';

export default {
  components: {
    PostCard,
  },
  data() {
    return {
      FollowedStories: [
        { id: 1, name: 'Sadie_m', image: "https://picsum.photos/seed/1/300/300" },
        { id: 2, name: 'zohi_code', image: 'https://picsum.photos/seed/2/300/300' },
        { id: 3, name: 'Nurse_na', image: 'https://picsum.photos/seed/3/300/300' },
        { id: 4, name: 'chicvibes', image: 'https://picsum.photos/seed/4/300/300' },
        { id: 5, name: 'voguevixen', image: 'https://picsum.photos/seed/5/300/300' },
        { id: 6, name: 'sophie_m', image: 'https://picsum.photos/seed/6/300/300' },
        { id: 7, name: 'sophie_m', image: 'https://picsum.photos/seed/7/300/300' },
        { id: 8, name: 'sophie_m', image: 'https://picsum.photos/seed/8/300/300' },
        // Diğer kullanıcılar burada olabilir...
      ],
      FollowedPosts: [
        {
          id: 1,
          user: 'Nurse_na',
          userImage: 'https://picsum.photos/seed/55/400/400',
          postImage: 'https://picsum.photos/seed/55/700/700',
          caption: 'This is a caption for post ...',
          likes: 140,
          comments: [
            { id: 1, user: 'Nurse_na', content: 'Comment 1' },
            { id: 2, user: 'chicvibes', content: 'Comment 2' },
            { id: 3, user: 'voguevixen', content: 'Comment 3' },
          ],
          shares: 0,
          timeAgo: '1 hour ago',
        },
        {
          id: 2,
          user: 'chicvibes',
          userImage: 'https://picsum.photos/seed/45/400/400',
          postImage: 'https://picsum.photos/seed/45/700/700',
          caption: 'This is a caption for post ...',
          likes: 1020,
          comments: [
            { id: 1, user: 'Nurse_na', content: 'Comment 1' },
            { id: 2, user: 'chicvibes', content: 'Comment 2' },
          ],
          shares: 2,
          timeAgo: '19 minutes ago',
        },
        {
          id: 3,
          user: 'lazy_baby',
          userImage: 'https://picsum.photos/seed/67/400/400/',
          postImage: 'https://picsum.photos/seed/67/700/700/',
          caption: 'This is a caption for.....',
          likes: 10,
          comments: [
            { id: 1, user: 'Nurse_na', content: 'Comment 1' },
            { id: 2, user: 'chicvibes', content: 'Comment 2' },
            { id: 3, user: 'lazy_baby', content: 'Comment 3' },
          ],
          shares: 2,
          timeAgo: '1 hour ago',
        },
        // Diğer kullanıcılar burada olabilir...
        // Diğer postlar burada olabilir...
      ],
    };
  },
};
</script>

<style scoped>
/* Hikayeler kısmında scroll barı gizleme */
.scrollbar-hide {
  -ms-overflow-style: none;
  /* IE ve Edge */
  scrollbar-width: none;
  /* Firefox */
}

.scrollbar-hide::-webkit-scrollbar {
  display: none;
  /* Chrome, Safari ve Opera */
}
</style>
