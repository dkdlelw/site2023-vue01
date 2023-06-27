<template>
  <section id="portSection" :class="attr">
    <div class="port__inner container">
      <div class="port__btn">
        <ul>
          <li :class="{ active: selectedTab === 'literature' }">
            <a href="#" @click="handleTabClick('literature')">문학</a>
          </li>
          <li :class="{ active: selectedTab === 'animation' }">
            <a href="#" @click="handleTabClick('animation')">애니메이션</a>
          </li>
          <li :class="{ active: selectedTab === 'movies' }">
            <a href="#" @click="handleTabClick('movies')">영화/드라마</a>
          </li>
          <li :class="{ active: selectedTab === 'games' }">
            <a href="#" @click="handleTabClick('games')">게임</a>
          </li>
        </ul>
      </div>
      <div class="port__cont">
        <div v-if="selectedTab === 'literature'">
          <div class="port" v-for="book in literatureBooks" :key="book.id">
            <figure class="port__header">
              <img :src="book.image" alt="포트폴리오" />
            </figure>
            <div class="port__body">
              <span class="pic">
                <img :src="book.memberImage" alt="멤버" />
              </span>
              <div class="title">
                <h4>{{ book.title }}</h4>
                <span>{{ book.author }}</span>
              </div>
            </div>
          </div>
        </div>
        <div v-if="selectedTab === 'animation'">
          <div class="port" v-for="animation in animations" :key="animation.id">
            <figure class="port__header">
              <a :href="animation.link">
                <img :src="animation.image" alt="애니메이션" />
              </a>
            </figure>
            <div class="port__body">
              <div class="title">
                <h4>{{ animation.title }}</h4>
                <span>{{ animation.description }}</span>
              </div>
            </div>
          </div>
        </div>
        <div v-if="selectedTab === 'movies'">
          <div class="port" v-for="movie in movies" :key="movie.id">
            <figure class="port__header">
              <a :href="movie.link">
                <img :src="movie.image" alt="영화" />
              </a>
            </figure>
            <div class="port__body">
              <div class="title">
                <h4>{{ movie.title }}</h4>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      selectedTab: "literature",
      literatureBooks: [
        {
          id: 1,
          image: "./assets/images/port/port_01.png",
          memberImage: "./assets/images/member/member01.jpg",
          title: "아이, 로봇",
          author: "아이작 아시모프(Isaac Asimov)",
        },
        {
          id: 2,
          image: "./assets/images/port/port_02.png",
          memberImage: "./assets/images/member/member02.jpg",
          title: "안드로이드는 전기양을 꿈꾸는가?",
          author: "필립 K. 딕 (Philip K. Dick)",
        },
        {
          id: 3,
          image: "./assets/images/port/port_03.png",
          memberImage: "./assets/images/member/member04.jpg",
          title: "스페이스 오디세이 2001",
          author: "아서 C. 클라크 (Stanley Kubrick)",
        },
        {
          id: 4,
          image: "./assets/images/port/port_04.png",
          memberImage: "./assets/images/member/member05.jpg",
          title: "1984",
          author: "조지 오웰(George Orwell)",
        },
        {
          id: 5,
          image: "./assets/images/port/port_05.png",
          memberImage: "./assets/images/member/member06.jpg",
          title: "듄",
          author: "프랭크 허버트(Frank Herbert)",
        },
        {
          id: 6,
          image: "./assets/images/port/port_06.png",
          memberImage: "./assets/images/member/member07.jpg",
          title: "11/22/63",
          author: "스티븐 킹(Stephen King)",
        },
      ],
      animations: [
        {
          id: 1,
          image: "./assets/images/port/port_02.png",
          link: "https://example.com/animation",
          title: "애니메이션 제목",
          description: "애니메이션 설명",
        },
        // Add other animations here
      ],
      movies: [
        {
          id: 1,
          image: "./assets/images/port/port_03.png",
          link: "https://example.com/movie",
          title: "영화 제목",
        },
        // Add other movies here
      ],
    };
  },
  methods: {
    handleTabClick(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>
<style lang="scss">
//port__wrap
.port__wrap {
}
.port__inner {
  .port__btn {
    margin-bottom: 20px;
    ul {
      display: flex;
      justify-content: center;
      li {
        a {
          border: 1px solid #9cd2ff;
          display: inline-block;
          padding: 5px 20px;
          margin: 0 5px;
          border-radius: 40px;
          color: #9cd2ff;
        }
      }
      li.active {
        a {
          color: #fff;
          background-color: #9cd2ff;
        }
      }
    }
  }

  .port__cont {
    @include flex-between;
    flex-wrap: wrap;

    .port {
      width: 32.2222%;
      margin-bottom: 30px;

      .port__body {
        display: flex;
        align-items: center;
        margin-top: 10px;
        text-align: left;

        .pic {
          width: 50px;
          height: 50px;
          margin: 15px 10px;
          border-radius: 50px;

          img {
            border-radius: 30px;
            width: 50px;
            height: 50px;
            object-fit: cover;
          }
        }

        .title {
          h4 {
            font-size: 24px;
            text-align: left;
          }
          span {
            font-size: 16px;
            color: #2c3a4b;
          }
        }
      }
      img {
        border-radius: 10px;
        width: 100%;
      }
      &:nth-child(1) .port__body .pic {
        background-color: #b9d1ff;
      }
      &:nth-child(2) .port__body .pic {
        background-color: #b9eeff;
      }
      &:nth-child(3) .port__body .pic {
        background-color: #ffb9ca;
      }
      &:nth-child(4) .port__body .pic {
        background-color: #f5ffb9;
      }
      &:nth-child(5) .port__body .pic {
        background-color: #cbffb9;
      }
      &:nth-child(6) .port__body .pic {
        background-color: #f5b9ff;
      }
      &:nth-child(4) {
        margin-bottom: 0;
      }
      &:nth-child(5) {
        margin-bottom: 0;
      }
      &:nth-child(6) {
        margin-bottom: 0;
      }
    }
  }
}
</style>
