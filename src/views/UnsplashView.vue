<template>
  <ContTitle title="images" />
  <UnsplashSlider />
  <UnsplashSearch />
  <UnsplashTag @search="SearchImages" />
  <UnsplashCont :images="images" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },
  setup() {
    const images = ref([]);

    const TopImages = async () => {
      await fetch(
        "https://api.unsplash.com/photos?client_id=UTTBntve3N_wMf-_VWO7RRnrOt3E4s3L9crRuJtSH1k&per_page=30"
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          images.value = result;
        })
        .catch((error) => console.log("error", error));
    };
    TopImages();
    const SearchImages = async (query) => {
      await fetch(
        `https://api.unsplash.com/search/photos?client_id=UTTBntve3N_wMf-_VWO7RRnrOt3E4s3L9crRuJtSH1k&per_page=30&q=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          images.value = result.results;
        })
        .catch((error) => console.log("error", error));
    };

    return {
      images,
      TopImages,
      SearchImages,
    };
  },
};
</script>
