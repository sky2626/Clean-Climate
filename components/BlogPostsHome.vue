<template>
  <div class="pt-8">
    <div class="flex items-center flex-col md:flex-row gap-[18px]">
      
        <BlogPost
        v-for="post in filteredPosts"
        :key="post.id"
        :title="post.title"
        :date="post.date"
        :content="post.content"
        :image="post.image"
        />
      
    </div>
  </div>
</template>

<script>
import BlogPost from '~/components/BlogPost.vue'

export default {
  components: {
    BlogPost
  },
  data() {
    return {
      searchQuery: '',
      currentPage: 1,
      postsPerPage: 5,
      posts: [
        { id: 1, title: 'Drought', date: '2024-08-04', content: "<p class='text-gray-400'>Drought is a prolonged period of abnormally low rainfall, leading to a shortage of water... </p>", image: 'https://cdn.pixabay.com/photo/2016/04/13/02/01/climate-change-1325882_1280.jpg' },
        { id: 2, title: 'Air Pollution', date: '2024-08-03', content: "<p class='text-gray-400'>Air pollution refers to the presence of harmful substances in the atmosphere....</p>", image: 'https://cdn.pixabay.com/photo/2022/11/06/23/39/climate-change-issue-7575216_1280.jpg' },
        { id: 2, title: 'Desertification', date: '2024-08-03', content: "<p class='text-gray-400'>Desertification refers to the process by which fertile land becomes desert...</p>", image: 'https://cdn.pixabay.com/photo/2012/11/06/15/40/tree-64310_1280.jpg' },
        // Add more posts here
      ]
    }
  },
  computed: {
    filteredPosts() {
      return this.posts.filter(post =>
        post.title.toLowerCase().includes(this.searchQuery.toLowerCase())
      ).slice((this.currentPage - 1) * this.postsPerPage, this.currentPage * this.postsPerPage)
    },
    totalPages() {
      return Math.ceil(this.posts.length / this.postsPerPage)
    }
  },
  methods: {
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage--
      }
    },
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++
      }
    }
  }
}
</script>
