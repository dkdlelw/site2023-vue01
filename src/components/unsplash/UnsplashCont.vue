<template>
  <div class="unsplash__cont container">
    <ul>
      <li v-for="(image, index) in images" :key="index">
        <a href="`https://unsplash.com/photos/${image.id}`">
          <img :src="image.urls.regular" :alt="image.alt_description" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    images: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style lang="scss">
//unsplash__wrap
.unsplash__wrap {
  overflow: hidden;
}
.unsplash__inner {
  height: 600px;

  .unsplash__text {
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
  .unsplash__item {
    @include flex-between;
    margin-top: 70px;
    position: absolute;

    > div {
      width: 400px;
      margin-right: 20px;
      img {
        width: 100%;
        @include border(20px);
      }
    }
  }
}

// unsplash__page
.unsplash__cont {
  ul {
    column-count: 4;

    li {
      margin-bottom: 20px;
    }
  }
}

//unsplash__search
.unsplash__search {
  text-align: center;
  margin-bottom: 50px;
  margin-top: 80px;

  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    @include border(50px);
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#0d86f7, #ffffff);
    @include border(50px);
  }
}
//tag
.unsplash__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    li {
      a {
        border: 1px solid #0d86f7;
        padding: 10px 20px;
        margin: 0 10px;
        color: #0d86f7;
      }
    }
  }
}
// slider
.unsplash__slider {
  height: 600px;
}
.unsplash__slider a img {
  object-fit: cover;
  //   margin-left: 10%;
  width: 1920px;
  height: 600px;
}
</style>
