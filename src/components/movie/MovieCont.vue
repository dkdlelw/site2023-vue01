<template>
  <div className="movie__cont container">
    <ul>
      <li v-for="(movie, index) in movies" :key="index">
        <a
          :href="`http://www.themoviedb.org/movie/${movie.id}`"
          target="_blank"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`"
            :alt="movie.title"
          />
          <em>
            <span class="title">{{ movie.title }}</span>
            <span class="star">{{ movie.vote_average }}</span>
          </em>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    movies: {
      type: Array,
      requierd: true,
    },
  },
};
</script>

<style lang="scss" scoped>
//movie__wrap
.movie__wrap {
  overflow: hidden;
}
.movie__inner {
  height: 700px;

  .movie__text {
    h3 {
      font-size: 50px;
      margin-bottom: 40px;
    }
    p {
      font-size: 22px;
      font-weight: 300;
      margin-bottom: 30px;
    }
    a {
      @include border(50px);
    }
  }
  .movie__item {
    @include flex-between;
    margin-top: 70px;
    position: absolute;

    > div {
      width: 250px;
      margin-right: 20px;

      img {
        width: 100%;
        @include border(20px);
      }
    }
  }
}
// movie__page
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;
    li {
      width: 23.3333%;
      margin-bottom: 4%;
      position: relative;
      img {
        width: 100%;
        border-radius: 20px;
        box-shadow: 0px 10px 10px #00000022;
      }
      em {
        .title {
          font-size: 20px;
          padding: 3px 0;
          &:hover {
            text-decoration: underline;
            text-underline-position: under;
          }
        }
        .star {
          position: absolute;
          right: 20px;
          top: 20px;
          width: 40px;
          height: 40px;
          background-color: #fff;
          text-align: center;
          line-height: 40px;
          border-radius: 50%;
          font-size: 15px;
          color: #4ba8ff;
        }
      }
      span {
        display: block;
        margin: 4px 0;
      }
    }
  }
}

//movie__search
.movie__search {
  text-align: center;
  margin-bottom: 50px;
  margin-top: 50px;
  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    @include border(50px);
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#00c183, #ffffff);
    @include border(50px);
  }
}
.movie__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    li {
      a {
        border: 1px solid #00c183;
        padding: 10px 20px;
        margin: 0 10px;
        color: #00c183;
      }
    }
  }
}
//movie__slider
// slider
.movie__slider {
  height: 1000px;
}
.movie__slider a img {
  object-fit: cover;
  justify-content: center;
  width: 1920px;
  height: 900px;
}
</style>
