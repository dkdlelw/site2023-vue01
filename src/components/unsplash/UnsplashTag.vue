<template>
  <div class="unsplash__tag container">
    <div>
      <button
        v-for="(tag, index) in unsplashTag"
        :key="index"
        @click="btnClick(tag.name)"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      unsplashTag: [
        { name: "SF", query: "Sience fiction" },
        { name: "사이버펑크", query: "cyberpunk" },
        { name: "스팀펑크", query: "steampunk" },
        { name: "포스트아포칼립스", query: "post apocalypse" },
        { name: "우주 오페라", query: "space opera" },
      ],
    };
  },
  methods: {
    btnClick(name) {
      this.$emit("search", name);
    },
  },
};
</script>

<style lang="scss">
.unsplash__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    button {
      border: 1px solid #0d86f7;
      padding: 10px 20px;
      margin: 0 10px;
      color: #0d86f7;
      background-color: #fff;
      cursor: pointer;

      &:hover {
        background-color: #0d86f7;
        color: #fff;
      }
    }
  }
}
</style>
