<template>
  <ContTitle title="movies" />
  <MovieSlider />
  <MovieSearch />
  <MovieTag />
  <MovieCont :movies="movies" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import MovieSlider from "@/components/movie/MovieSlider.vue";
import MovieSearch from "@/components/movie/MovieSearch.vue";
import MovieTag from "@/components/movie/MovieTag.vue";
import MovieCont from "@/components/movie/MovieCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    MovieSlider,
    MovieSearch,
    MovieTag,
    MovieCont,
  },
  setup() {
    const movies = ref([]);
    const searchs = ref([]);
    const search = ref("cyberpuk movie");

    const TopMovies = async () => {
      await fetch(
        `https://api.themoviedb.org/3/movie/popular?api_key=37bef2f4ca3f23b3e4f635f2ec51d2a4&language=ko-KR&query=${search.value}`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          movies.value = result.results;
          searchs.value = result.results;
          console.log(searchs);
        })
        .catch((error) => console.log("error", error));
    };
    TopMovies();

    return {
      movies,
      searchs,
      TopMovies,
    };
  },
};
</script>
