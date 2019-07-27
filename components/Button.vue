<template>
  <div class="w-full block" :class="[this.buttonPosition, this.paddingYDefault]">
    <a
      :href="this.href"
      class="border border-white px-12 py-5 hover:text-black hover:bg-white font-normal"
    >{{title}}</a>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    paddingY: String,
    position: String,
    title: String,
    href: String
  },
  computed: {
    paddingYDefault: function() {
      if (this.paddingY) {
        return this.paddingY;
      } else {
        return 'py-16';
      }
    },
    buttonPosition: function() {
      switch (this.position) {
        case 'left':
          return '';
          break;
        case 'right':
          return 'text-right';
          break;
        default:
          return 'text-center';
        // code block
      }
    }
  }
};
</script>

<style scoped>
</style>


