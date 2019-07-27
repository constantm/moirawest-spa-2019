<template>
  <div class="bg-gray-800 text-white">
    <Swiper
      :slideshow_portrait="story.content.slideshow_portrait"
      :slideshow_landscape="story.content.slideshow_landscape"
    />
    <div class="row">
      <div class="container mx-auto">
        <h2>{{ story.content.intro_heading }}</h2>
        <div v-html="story.content.intro_copy.content"></div>
      </div>
    </div>

    <div class="row">
      <div class="container mx-auto">
        <div class="flex flex-wrap">
          <div class="w-full lg:w-2/3">
            <img src="@/assets/about-moira.png" alt />
          </div>
          <div class="w-full pl-0 lg:pl-12 lg:w-1/3">
            <h2>{{ story.content.about_me_heading }}</h2>
            <div v-html="story.content.about_me_excerpt.content"></div>
            <p>
              <a href="#" class="block text-center w-100">More about me</a>
            </p>
          </div>
        </div>
      </div>
    </div>

    <ThumbnailGallery :blogPosts="featuredBlogPosts" />

    <Testimonials />

    <div
      class="image-block w-100 md:hidden overflow-hidden relative bg-cover bg-center bg-no-repeat"
      style="background-image:url(https://moirawest.com/media/2019/06/Jake-Jordy01.jpg)"
    >
      <div class="absolute h-full z-50 w-full">
        <div class="container mx-auto h-full flex flex-wrap content-center">
          <h2>Wedding</h2>
          <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
          <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
          <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
        </div>

        <Button href="#" title="The Experience" />
      </div>
    </div>
    <div
      class="image-block w-100 hidden md:block overflow-hidden relative bg-cover bg-center bg-no-repeat"
      style="background-image:url(https://moirawest.com/media/2019/06/Jake-Jordy01.jpg)"
    >
      <div class="absolute h-full z-50 w-full top-1/3">
        <div class="container mx-auto">
          <h2>Wedding</h2>
          <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
          <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
          <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
        </div>
        <Button href="#" title="The Experience" />
      </div>
    </div>

    <div class="w-100">
      <div class="h-full z-50 w-full py-10">
        <h4>Have some questions? Just want to say hello?</h4>
        <Button href="#" title="Get in touch" paddingY="pt-10 pb-5" />
      </div>
    </div>

    <div id="social-media" class="text-center">
      <h4 class="my-4">
        <a
          href="https://www.instagram.com/moirawestphotography"
          target="_blank"
          title="Moira West Photography on Instagram"
        >@moirawestphotography</a>
      </h4>

      <vue-instagram
        token="2243925994.1677ed0.c242caf4229e450f9a8cdaefaadf2076"
        :count="6"
        mediaType="image"
        class="flex flex-wrap"
      >
        <template slot="feeds" slot-scope="props">
          <a
            :href="props.feed.link"
            :title="hrefTitle(props)"
            class="w-1/2 md:w-1/6 h-48 bg-center bg-no-repeat bg-cover"
            :style="{ backgroundImage: 'url('+props.feed.images.standard_resolution.url+')' }"
          ></a>
        </template>
        <template slot="error" slot-scope="props"></template>
      </vue-instagram>

      <InstagramSvg class="mx-1 my-5 social-icon" />
      <FacebookSvg class="mx-1 my-5 social-icon" />
    </div>
  </div>
</template>

<script>
import _ from "lodash";
import VueInstagram from "vue-instagram";

// Social icons
import InstagramSvg from "@/assets/instagram.svg";
import FacebookSvg from "@/assets/facebook.svg";

import Swiper from "@/components/Swiper";
import Button from "@/components/Button";
import ThumbnailGallery from "@/components/ThumbnailGallery";
import Testimonials from "@/components/Testimonials";

export default {
  name: "Home",
  components: {
    Swiper,
    Button,
    ThumbnailGallery,
    Testimonials,
    InstagramSvg,
    FacebookSvg
  },
  props: {
    msg: String
  },
  methods: {
    hrefTitle: props => {
      return `${props.feed.user.full_name} ${props.feed.caption.text}`;
    }
  },
  data() {
    return {
      story: { content: {} },
      links: {},
      stories: {},
      featuredBlogPosts: []
    };
  },
  async asyncData(context) {
    let home = await context.app.$storyapi.get("cdn/stories/home").then(res => {
      return res.data;
    });

    let featuredBlogPostLinks = home.story.content.featured_blog_posts;

    let featuredBlogPostsObjects = await context.app.$storyapi.get("cdn/links").then(function(res) {
        return _.filter(res.data.links, function(link, key) {
          return _.includes(featuredBlogPostLinks, key);
        });
    });

    let featuredBlogPostIds = _.map(featuredBlogPostsObjects, 'uuid') 

    let featuredBlogPosts = await context.app.$storyapi.get("cdn/stories", {
      by_uuids: featuredBlogPostIds
    }).then(function(res) {
      return res.data.stories
    });

    return { story: home.story, featuredBlogPosts: featuredBlogPosts };
  }
};
</script>

<style scoped>
.image-block {
  height: 90vh;
}
.min-width-wide {
  min-width: 1170px;
}
.social-icon {
  fill: #fff;
  max-width: 1.5em;
  display: inline-block;
}
</style>
