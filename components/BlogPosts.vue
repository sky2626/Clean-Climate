<template>
  <div class="pt-8">
    <input
      type="text"
      v-model="searchQuery"
      placeholder="Search..."
      class="mb-4 p-2 border border-1 border-green-600 bg-white focus:ring-green-500 focus:border-green-500 rounded-lg"
    />
    <div class="">
      <BlogPost
        v-for="post in filteredPosts"
        :key="post.id"
        :title="post.title"
        :date="post.date"
        :content="post.content"
        :image="post.image"
      />
    </div>
    <div class="flex justify-between mt-4">
      <button
        @click="prevPage"
        :disabled="currentPage === 1"
        class="px-4 py-2 bg-green-600 rounded"
      >
        Previous
      </button>
      <button
        @click="nextPage"
        :disabled="currentPage === totalPages"
        class="px-4 py-2 bg-green-600 rounded"
      >
        Next
      </button>
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
        { id: 1, title: 'First Post', date: '2024-08-04', content: "<p class='text-gray-400'>This is the first post content.</p>", image: 'https://cdn.pixabay.com/photo/2016/04/13/02/01/climate-change-1325882_1280.jpg' },
        { id: 2, title: 'Second Post', date: '2024-08-03', content: "<p class='text-gray-400'>This is the second post content.</p>", image: 'https://cdn.pixabay.com/photo/2019/12/09/19/39/pxclimateaction-4684217_1280.jpg' },
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
