<template>
  <ContTitle title="youtube" />
  <YoutubeSearch @search="SearchYoutube" />
  <YoutubeTag @search="SearchYoutube" />
  <YoutubeCont :youtubes="youtubes" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },
  setup() {
    const youtubes = ref([]);

    const TopYoutubes = async () => {
      await fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=cyberpunk&type=video&key=AIzaSyA7K99aX_UKS2VDnyAlhnk6NApN4cHFfKg"
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          youtubes.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };
    TopYoutubes();

    const SearchYoutube = async (query) => {
      await fetch(
        `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=${query}type=video&key=AIzaSyA7K99aX_UKS2VDnyAlhnk6NApN4cHFfKg`
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };

    return {
      youtubes,
      TopYoutubes,
      SearchYoutube,
    };
  },
};
</script>
