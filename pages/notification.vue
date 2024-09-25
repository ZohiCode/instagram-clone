<template>
  <div class="pt-14  p-4">
    <div class=" min-h-screen p-2 pt-4">
      <h1 class="text-2xl font-bold mb-4">Notifications</h1>
      <div class="space-y-2">
        <NotificationCard v-for="message in FollowerNotificationMessages" :key="message.id" :message="message" />
        
      </div>
    </div>
  </div>
</template>

<script>
import NotificationCard from '@/components/NotificationCard.vue';

export default {
  components: {
    NotificationCard,
  },
  data() {
    return {
      FollowerNotificationMessages: [
        {
          id: 1,
          from: 'John Doe',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/244/100/100',
          timeAgo: '12 minutes ago',
          day: 'Today',
        },
        {
          id: 2,
          from: 'Jane Smith',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/342/100/100',
          timeAgo: '1 minute ago',
          day: 'Today',
        },
        {
          id: 3,
          from: 'Bob Johnson',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/232/100/100',
          timeAgo: '2 hours ago',
          day: 'Yesterday',
        },
        {
          id: 4,
          from: 'Sarah Williams',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/1232/100/100',
          timeAgo: '3 hours ago',
          day: 'Yesterday',
        },
        {
          id: 5,
          from: 'Michael Brown',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/123/100/100',
          timeAgo: '4 hours ago',
          day: 'Yesterday',
        },
        {
          id: 6,
          from: 'Emily Davis',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/123/100/100',
          timeAgo: '5 hours ago',
          day: 'Yesterday',
        },
        {
          id: 7,
          from: 'David Wilson',
          content: 'started following you.',
          image: 'https://picsum.photos/seed/123/100/100',
          timeAgo: '6 hours ago',
          day: 'Yesterday',
        },
      ],
    };
  },
};
</script>
