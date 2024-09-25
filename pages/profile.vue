<template>
  <div class="mx-auto px-4 max-w-screen-lg">
    <!-- Profile Header -->
    <div class="flex flex-col md:flex-row items-center pt-10  p-4">
      <img :src="user.profilePicture" alt="Profile Picture"
        class="w-24 h-24 md:w-32 md:h-32 rounded-full border-2 border-gray-300" />
      <div class="md:ml-24 w-full mt-4 md:mt-0 text-center md:text-left">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <h1 class="text-xl md:text-2xl font-regular">{{ user.username }}</h1>
          <div class="flex space-x-4 items-center mt-2 ">
            <div class="bg-gray-200 text-center px-4 py-2 rounded-lg text-sm">Follow</div>
            <div class="bg-gray-200 text-center px-4 py-2 rounded-lg text-sm">Send Message</div>
            <svg class="rotate-90 h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M12 5v.01M12 12v.01M12 19v.01M12 6a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
            </svg>
          </div>
        </div>
        <div class="flex justify-center md:justify-start space-x-8 mt-4">
          <div><span class="font-bold">{{ user.posts.length }}</span> posts</div>
          <div><span class="font-bold">{{ user.followers }}</span> followers</div>
          <div><span class="font-bold">{{ user.following }}</span> following</div>
        </div>
        <p class="mt-2" v-html="user.bio"></p>
      </div>
    </div>

    <!-- Highlights -->
    <div class="flex flex-wrap justify-center md:justify-start mt-4 space-x-2 md:space-x-4">
      <div v-for="highlight in highlights" :key="highlight.id" class="flex flex-col items-center mb-4">
        <img :src="highlight.image" :alt="highlight.title"
          class="w-16 h-16 md:w-20 md:h-20 rounded-full border-2 border-gray-300 cursor-pointer" />
        <span class="text-xs mt-2">{{ highlight.title }}</span>
      </div>
    </div>

    <!-- Tab Navigation -->
    <div class="flex justify-center mt-6 space-x-6">
      <div @click="activeTab = 'posts'"
        :class="{ 'border-b-2 border-blue-500 font-semibold': activeTab === 'posts', 'text-gray-500': activeTab !== 'posts' }"
        class="cursor-pointer py-2">Posts</div>
      <div @click="activeTab = 'videos'"
        :class="{ 'border-b-2 border-blue-500 font-semibold': activeTab === 'videos', 'text-gray-500': activeTab !== 'videos' }"
        class="cursor-pointer py-2">Videos</div>
      <div @click="activeTab = 'likes'"
        :class="{ 'border-b-2 border-blue-500 font-semibold': activeTab === 'likes', 'text-gray-500': activeTab !== 'likes' }"
        class="cursor-pointer py-2">Likes</div>
    </div>

    <!-- Content Section -->
    <div class="mt-6">
      <div v-if="activeTab === 'posts'">
        <div class="grid grid-cols-2 sm:grid-cols-3 gap-2 md:gap-4 mt-4">
          <PostCard v-for="post in userPosts" :key="post.id" :post="post" class="bg-white border rounded-lg shadow-md" />
        </div>
      </div>
      <div v-if="activeTab === 'videos'">
        <div class="grid grid-cols-2 sm:grid-cols-3 gap-2 md:gap-4 mt-4">
          <PostCard v-for="post in userVideos" :key="post.id" :post="post" class="bg-white border rounded-lg shadow-md" />
        </div>
      </div>
      <div v-if="activeTab === 'likes'">
        <div class="grid grid-cols-2 sm:grid-cols-3 gap-2 md:gap-4 mt-4">
          <PostCard v-for="post in userLilkes" :key="post.id" :post="post" class="bg-white border rounded-lg shadow-md" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PostCard from '~/components/PostCard.vue';

export default {
  components: {
    PostCard,
  },

  methods: {
    nextLine(str) {
      return str.split('|').join('<br> ');
    },
  },

  data() {
    return {
      activeTab: 'posts',
      user: {
        username: 'ZohiCode',
        bio: this.nextLine("✨️💻☕️🍃|Software-Study-Work✨|-Remote web developer 🖥️|-Freelance mobile developer 📱|💌 : Collabs & Collaboration 👉🏻DM"),
        profilePicture: 'https://picsum.photos/seed/100/100', // Replace with actual URL
        followers: 7.4120,
        following: 375,
        posts: [ // Use this array to count posts
          { id: 1, title: 'User Post 1', content: 'Content 1', image: 'https://picsum.photos/seed/post1/400/400' },
          { id: 2, title: 'User Post 2', content: 'Content 2', image: 'https://picsum.photos/seed/post2/400/400' },
          // Add more posts as needed
        ],
      },
      userPosts: [
        { id: 1, title: 'User Post 1', content: 'Content 1', image: 'https://picsum.photos/seed/post1/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 2, title: 'User Post 2', content: 'Content 2', image: 'https://picsum.photos/seed/post2/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 3, title: 'User Post 3', content: 'Content 3', image: 'https://picsum.photos/seed/post3/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 4, title: 'User Post 4', content: 'Content 4', image: 'https://picsum.photos/seed/post4/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 5, title: 'User Post 5', content: 'Content 5', image: 'https://picsum.photos/seed/post5/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 6, title: 'User Post 6', content: 'Content 6', image: 'https://picsum.photos/seed/post6/400/400', likes: 0, comments: 0, shares: 0 },
        // Add more posts as needed
      ],
      userVideos: [
        { id: 1, title: 'User Video 1', image: 'https://picsum.photos/seed/133/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 2, title: 'User Video 2', image: 'https://picsum.photos/seed/233/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 3, title: 'User Video 3', image: 'https://picsum.photos/seed/253/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 4, title: 'User Video 4', image: 'https://picsum.photos/seed/284/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 5, title: 'User Video 5', image: 'https://picsum.photos/seed/533/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 6, title: 'User Video 6', image: 'https://picsum.photos/seed/633/400/400', likes: 0, comments: 0, shares: 0 },
        // Add more posts as needed
      ],
      userLilkes: [
        { id: 6, title: 'User Video 6', image: 'https://picsum.photos/seed/63/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 7, title: 'User Video 7', image: 'https://picsum.photos/seed/73/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 8, title: 'User Video 8', image: 'https://picsum.photos/seed/83/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 9, title: 'User Video 9', image: 'https://picsum.photos/seed/93/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 10, title: 'User Video 10', image: 'https://picsum.photos/seed/13/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 11, title: 'User Video 11', image: 'https://picsum.photos/seed/32/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 12, title: 'User Video 12', image: 'https://picsum.photos/seed/23/400/400', likes: 0, comments: 0, shares: 0 },
        { id: 13, title: 'User Video 13', image: 'https://picsum.photos/seed/53/400/400', likes: 0, comments: 0, shares: 0 },
        // Add more posts as needed 
      ],
      highlights: [
        { id: 1, title: 'Highlight', image: 'https://picsum.photos/seed/2/100/100' },
        { id: 2, title: 'life', image: 'https://picsum.photos/seed/450/100/100' },
        { id: 3, title: 'School', image: 'https://picsum.photos/seed/667/100/100' },
        { id: 4, title: 'Software✨', image: 'https://picsum.photos/seed/60/100/100' },
        { id: 5, title: 'Food', image: 'https://picsum.photos/seed/350/100/100' },
      ],
    };
  },
};
</script>

<style scoped></style>
