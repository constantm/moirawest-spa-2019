<template>
  <div class="row mb-0 pb-0 lg:pb-12 lg:mb-2">
    <div class="container mx-auto">
      <div class="flex flex-wrap thumbnails">
        <img
          v-for="blog in blogPosts"
          :key="blog.id"
          class="w-full lg:w-1/3 pb-1 lg:pb-4"
          :src="blog.content.featured_image_square"
          :alt="blog.content.title"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ThumbnailGallery",
  props: {
    blogPosts: Array
  },
  data() {
    return {
      stories: [],
      links: []
    }
  }
};
</script>

<style scoped>
@screen lg {
  .thumbnails img:nth-child(1),
  .thumbnails img:nth-child(2),
  .thumbnails img:nth-child(4),
  .thumbnails img:nth-child(5) {
    @apply pr-4;
  }
}
</style>


