<template>
  <section id="movieSection" :class="attr">
    <div class="movie__inner">
      <div class="movie__text container">
        <h3>SF 추천 영화</h3>
        <p>
          SF장르를 기반으로 한 영화들을 추천합니다.<br />더 많은 정보들은 자세히
          보기를 눌러주세요.
        </p>
        <router-link to="#" class="button-green">자세히 보기</router-link>
        <div class="movie__item">
          <div>
            <img src="@/assets/images/movie/movie01.png" alt="영화" />
          </div>
          <div>
            <img src="@/assets/images/movie/movie02.png" alt="영화" />
          </div>
          <div>
            <img src="@/assets/images/movie/movie03.png" alt="영화" />
          </div>
          <div>
            <img src="@/assets/images/movie/movie04.png" alt="영화" />
          </div>
          <div>
            <img src="@/assets/images/movie/movie05.png" alt="영화" />
          </div>
          <div>
            <img src="@/assets/images/movie/movie06.png" alt="영화" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    attr: String,
  },
};
</script>
<style lang="scss">
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
//movie__page
.movie__page {
}
.movie__slider {
  display: none;
}
.movie__search {
  text-align: center;
  margin-bottom: 50px;

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
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;

    li {
      width: 15%;
      margin-bottom: 4%;

      span {
        display: block;
        margin: 4px 0;
      }
    }
  }
}
</style>
