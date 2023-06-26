<template>
  <div class="youtube__tag container">
    <div>
      <button
        v-for="(tag, index) in youtubeTag"
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
      youtubeTag: [
        { name: "바이오펑크" },
        { name: "사이버펑크" },
        { name: "스팀펑크" },
        { name: "포스트아포칼립스" },
        { name: "우주 오페라" },
      ],
    };
  },
  methods: {
    btnClick(name) {
      if (this.$props.onSearch) {
        this.$props.onSearch(name);
      }
    },
  },
  props: {
    onSearch: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.youtube__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    button {
      border: 1px solid #f7100d;
      padding: 10px 20px;
      margin: 0 10px;
      color: #f7100d;
      background-color: #fff;
      cursor: pointer;

      &:hover {
        background-color: #f7100d;
        color: #fff;
      }
    }
  }
}
</style>
