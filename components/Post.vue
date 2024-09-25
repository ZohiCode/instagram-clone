<template>
    <div class="bg-white rounded-lg mb-6 max-w-3xl mx-auto p-2 px-4">
        <!-- User info -->
        <div class="flex items-center py-2">
            <img :src="post.userImage" alt="User avatar" class="w-14 h-14 rounded-full object-cover" />
            <div class="ml-4">
                <span class="font-semibold block">{{ post.user }}</span>
                <span class="text-sm text-gray-500">{{ post.time }}</span> <!-- Post time ekledik -->
            </div>
        </div>

        <!-- Post image -->
        <div class="w-full max-h-[600px] overflow-hidden rounded">
            <img @dblclick="toggleLike" :src="post.postImage" alt="Post image" class="w-full h-auto object-cover" />
        </div>

        <!-- Post caption and interactions -->
        <div class="p-4 space-y-2">
            <!-- Interactions (like, comment, share) -->
            <div class="flex justify-between items-center">
                <div class="flex space-x-4">
                    <button class="focus:outline-none" @click="toggleLike">
                        <svg width="38px" height="38px" viewBox="-0.5 0 25 25" :fill="liked ? 'red' : 'none'"
                            xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M15.6001 3.91998C14.268 3.92397 12.9849 4.42297 12 5.32001C11.2277 4.61746 10.2676 4.15485 9.23679 3.98858C8.20602 3.82231 7.1491 3.95955 6.19498 4.3836C5.24087 4.80765 4.43081 5.50018 3.8635 6.37671C3.29619 7.25324 2.99614 8.27591 3.00004 9.32C3.00004 15.77 12 20.14 12 20.14C12 20.14 21 15.77 21 9.32C21 7.88784 20.4311 6.51434 19.4184 5.50165C18.4057 4.48895 17.0322 3.91998 15.6001 3.91998Z"
                                :stroke="liked ? 'red' : '#000000'" stroke-width="1.5" stroke-linecap="round"
                                stroke-linejoin="round" />
                        </svg> </button>
                    <button class="focus:outline-none">
                        <svg width="35px" height="35px" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <g clip-path="url(#clip0_8_53)">
                                <path
                                    d="M16 12C15.87 12.0016 15.7409 11.9778 15.62 11.93C15.4971 11.8781 15.3852 11.8035 15.29 11.7101C15.2001 11.6179 15.1287 11.5092 15.08 11.39C15.0296 11.266 15.0025 11.1338 15 11C15.0011 10.7376 15.1053 10.4863 15.29 10.3C15.3825 10.2033 15.4952 10.1282 15.62 10.0801C15.8031 10.0047 16.0044 9.98535 16.1984 10.0245C16.3924 10.0637 16.5705 10.1596 16.71 10.3C16.8947 10.4863 16.9989 10.7376 17 11C16.9975 11.1338 16.9704 11.266 16.92 11.39C16.8713 11.5092 16.7999 11.6179 16.71 11.7101C16.6166 11.8027 16.5057 11.876 16.3839 11.9258C16.2621 11.9755 16.1316 12.0007 16 12Z"
                                    fill="#000000" />
                                <path
                                    d="M12 12C11.87 12.0016 11.7409 11.9778 11.62 11.93C11.4971 11.8781 11.3852 11.8035 11.29 11.7101C11.2001 11.6179 11.1287 11.5092 11.08 11.39C11.0296 11.266 11.0025 11.1338 11 11C11.0011 10.7376 11.1053 10.4863 11.29 10.3C11.3825 10.2033 11.4952 10.1282 11.62 10.0801C11.8031 10.0047 12.0044 9.98535 12.1984 10.0245C12.3924 10.0637 12.5705 10.1596 12.71 10.3C12.8947 10.4863 12.9989 10.7376 13 11C12.9975 11.1338 12.9704 11.266 12.92 11.39C12.8713 11.5092 12.7999 11.6179 12.71 11.7101C12.6166 11.8027 12.5057 11.876 12.3839 11.9258C12.2621 11.9755 12.1316 12.0007 12 12Z"
                                    fill="#000000" />
                                <path
                                    d="M8 12C7.86999 12.0016 7.74091 11.9778 7.62 11.93C7.49713 11.8781 7.38519 11.8035 7.29001 11.7101C7.20006 11.6179 7.12873 11.5092 7.07999 11.39C7.0296 11.266 7.0025 11.1338 7 11C7.0011 10.7376 7.10526 10.4863 7.29001 10.3C7.3825 10.2033 7.49516 10.1282 7.62 10.0801C7.80305 10.0047 8.00435 9.98535 8.19839 10.0245C8.39244 10.0637 8.57048 10.1596 8.70999 10.3C8.89474 10.4863 8.9989 10.7376 9 11C8.9975 11.1338 8.9704 11.266 8.92001 11.39C8.87127 11.5092 8.79994 11.6179 8.70999 11.7101C8.61655 11.8027 8.50575 11.876 8.38391 11.9258C8.26207 11.9755 8.13161 12.0007 8 12Z"
                                    fill="#000000" />
                            </g>
                            <path
                                d="M4.99951 16.55V19.9C4.99922 20.3102 5.11905 20.7114 5.34418 21.0542C5.56931 21.397 5.88994 21.6665 6.26642 21.8292C6.6429 21.9919 7.05875 22.0408 7.46271 21.9698C7.86666 21.8989 8.24103 21.7113 8.53955 21.4301L11.1495 18.9701H12.0195C17.5395 18.9701 22.0195 15.1701 22.0195 10.4701C22.0195 5.77009 17.5395 1.97009 12.0195 1.97009C6.49953 1.97009 2.01953 5.78009 2.01953 10.4701C2.042 11.6389 2.32261 12.7882 2.84125 13.8358C3.35989 14.8835 4.10373 15.8035 5.01953 16.53L4.99951 16.55Z"
                                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                            <defs>
                                <clipPath id="clip0_8_53">
                                    <rect width="10" height="2" fill="white" transform="translate(7 10)" />
                                </clipPath>
                            </defs>
                        </svg>
                    </button>
                    <button class="focus:outline-none">
                        <svg width="35px" height="35px" viewBox="-0.5 0 25 25" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M2.33045 8.38999C0.250452 11.82 9.42048 14.9 9.42048 14.9C9.42048 14.9 12.5005 24.07 15.9305 21.99C19.5705 19.77 23.9305 6.13 21.0505 3.27C18.1705 0.409998 4.55045 4.74999 2.33045 8.38999Z"
                                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
                            <path d="M15.1999 9.12L9.41992 14.9" stroke="#000000" stroke-width="1.5" stroke-linecap="round"
                                stroke-linejoin="round" />
                        </svg> </button>
                </div>
                <button class="focus:outline-none" @click="toggleSave">
                    <svg width="35px" height="35px" viewBox="-0.5 0 25 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M16 10.99L13.1299 14.05C12.9858 14.2058 12.811 14.3298 12.6166 14.4148C12.4221 14.4998 12.2122 14.5437 12 14.5437C11.7878 14.5437 11.5779 14.4998 11.3834 14.4148C11.189 14.3298 11.0142 14.2058 10.87 14.05L8 10.99"
                            stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" fill="" />
                        <path
                            d="M21 17.4199V7.41992C21 5.21078 19.2091 3.41992 17 3.41992L7 3.41992C4.79086 3.41992 3 5.21078 3 7.41992V17.4199C3 19.6291 4.79086 21.4199 7 21.4199H17C19.2091 21.4199 21 19.6291 21 17.4199Z"
                            :stroke="saved ? 'none' : '#000000'" stroke-width="1.5" stroke-linecap="round"
                            stroke-linejoin="round" />
                    </svg>
                </button>
            </div>

            <!-- Likes -->
            <div class="text-sm font-semibold">
                {{ post.likes }} likes
            </div>

            <!-- Post caption -->
            <div>
                <span class="font-semibold">{{ post.user }}</span>
                <span class="ml-2 text-sm">{{ post.caption }}</span>
            </div>

            <!-- Post comments (optional) -->
            <div v-if="post.comments && post.comments.length" class="text-sm text-gray-500">
                View all {{ post.comments.length }} comments
            </div>

            <!-- Post time -->
            <div class="text-xs text-gray-400">{{ post.timeAgo }}</div>
        </div>
    </div>
</template>
  
<script>
export default {
    props: {
        post: Object,
    },
    data() {
        return {
            liked: false,
            saved: false,
        };
    },
    methods: {
        toggleLike() {
            this.liked = !this.liked;
            this.post.likes += this.liked ? 1 : -1;
        },
        toggleSave() {
            this.saved = !this.saved;
        },
    },
};
</script>
  
<style scoped>
/* Ekstra responsive tweaks burada yapılabilir */
</style>
  