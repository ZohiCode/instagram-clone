<template>
  <div class="p-2">
    <div class="pt-8 grid grid-cols-2 sm:grid-cols-3 md:grid-cols-3 lg:grid-cols-4 gap-1">
      <PostCard v-for="post in trendingPosts" :key="post.id" :post="post"
        class="transition-transform transform hover:scale-125 hover:z-40 duration-1000 ease-in-out" />
    </div>
  </div>
</template>

<script>
import PostCard from '~/components/PostCard.vue';

export default {
  components: {
    PostCard,
  },
  data() {
    return {
      trendingPosts: [
        { id: 1, title: 'Post 1', content: 'Content 1', image: 'https://picsum.photos/seed/post1/400/400', likes: 10, comments: 5, shares: 2 },
        { id: 2, title: 'Post 2', content: 'Content 2', image: 'https://picsum.photos/seed/post2/400/400', likes: 20, comments: 10, shares: 5 },
        { id: 3, title: 'Post 3', content: 'Content 3', image: 'https://picsum.photos/seed/post3/400/400', likes: 15, comments: 8, shares: 3 },
        { id: 4, title: 'Post 4', content: 'Content 4', image: 'https://picsum.photos/seed/post4/400/400', likes: 12, comments: 7, shares: 4 },
        { id: 5, title: 'Post 5', content: 'Content 5', image: 'https://picsum.photos/seed/post5/400/400', likes: 18, comments: 9, shares: 6 },
        { id: 6, title: 'Post 6', content: 'Content 6', image: 'https://picsum.photos/seed/post6/400/400', likes: 25, comments: 12, shares: 8 },
        // Add more posts as neede
        { id: 7, title: 'Post 7', content: 'Content 7', image: 'https://picsum.photos/seed/post7/400/400', likes: 30, comments: 15, shares: 10 },
        { id: 8, title: 'Post 8', content: 'Content 8', image: 'https://picsum.photos/seed/post8/400/400', likes: 35, comments: 18, shares: 12 },
        { id: 9, title: 'Post 9', content: 'Content 9', image: 'https://picsum.photos/seed/post9/400/400', likes: 40, comments: 20, shares: 14 },
        { id: 10, title: 'Post 10', content: 'Content 10', image: 'https://picsum.photos/seed/post10/400/400', likes: 45, comments: 22, shares: 16 },
        { id: 11, title: 'Post 11', content: 'Content 11', image: 'https://picsum.photos/seed/post11/400/400', likes: 50, comments: 25, shares: 18 },
        { id: 12, title: 'Post 12', content: 'Content 12', image: 'https://picsum.photos/seed/post12/400/400', likes: 55, comments: 27, shares: 20 },
        // Add more posts as needed
        { id: 13, title: 'Post 13', content: 'Content 13', image: 'https://picsum.photos/seed/post13/400/400', likes: 60, comments: 30, shares: 22 },
        { id: 14, title: 'Post 14', content: 'Content 14', image: 'https://picsum.photos/seed/post14/400/400', likes: 65, comments: 32, shares: 24 },
        { id: 15, title: 'Post 15', content: 'Content 15', image: 'https://picsum.photos/seed/post15/400/400', likes: 70, comments: 35, shares: 26 },
        { id: 16, title: 'Post 16', content: 'Content 16', image: 'https://picsum.photos/seed/post16/400/400', likes: 75, comments: 37, shares: 28 },
        { id: 17, title: 'Post 17', content: 'Content 17', image: 'https://picsum.photos/seed/post17/400/400', likes: 80, comments: 40, shares: 30 },
        { id: 18, title: 'Post 18', content: 'Content 18', image: 'https://picsum.photos/seed/post18/400/400', likes: 85, comments: 42, shares: 32 },
        // Add more posts as needed
        { id: 19, title: 'Post 19', content: 'Content 19', image: 'https://picsum.photos/seed/post19/400/400', likes: 90, comments: 45, shares: 35 },
        { id: 20, title: 'Post 20', content: 'Content 20', image: 'https://picsum.photos/seed/post20/400/400', likes: 95, comments: 47, shares: 37 },
        { id: 21, title: 'Post 21', content: 'Content 21', image: 'https://picsum.photos/seed/post21/400/400', likes: 100, comments: 50, shares: 39 },
        { id: 22, title: 'Post 22', content: 'Content 22', image: 'https://picsum.photos/seed/post22/400/400', likes: 105, comments: 52, shares: 41 },
        { id: 23, title: 'Post 23', content: 'Content 23', image: 'https://picsum.photos/seed/post23/400/400', likes: 110, comments: 55, shares: 43 },
        { id: 24, title: 'Post 24', content: 'Content 24', image: 'https://picsum.photos/seed/post24/400/400' },
        // Add more posts as needed
      ],
    };
  },
};
</script>

<style scoped>
/* Gerekirse ek stil ayarları buraya ekleyebilirsiniz */
</style>
