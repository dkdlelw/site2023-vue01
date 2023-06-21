<template>
  <section id="portSection" :class="attr">
    <h3>SF 작품 소개</h3>
    <p>각 유명작품들을 소개합니다.</p>
    <div class="port__inner container">
      <div class="port__btn">
        <ul>
          <li class="active"><a href="#">문학</a></li>
          <li><a href="#">애니메이션</a></li>
          <li><a href="#">영화/드라마</a></li>
          <li><a href="#">게임</a></li>
        </ul>
      </div>
      <div class="port__cont">
        <div class="port" v-for="(text, index) in texts" :key="index">
          <figure class="port__header">
            <img :src="text.img" :alt="text.title" />
          </figure>
          <div class="port__body">
            <span class="pic">
              <img :src="text.icon" :alt="text.title" />
            </span>
            <div class="title">
              <h4>{{ text.title }}</h4>
              <span>{{ text.desc }}</span>
            </div>
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
  data: function () {
    return {
      texts: [
        {
          img: "./images/port/port_01.png",
          title: "아이, 로봇",
          desc: "아이작 아시모프(Isaac Asimov)",
          icon: "./images/member/member01.jpg",
        },
        {
          img: "./images/port/port_02.png",
          title: "안드로이드는 전기양을 꿈꾸는가?",
          desc: "필립 K. 딕 (Philip K. Dick)",
          icon: "./images/member/member02.jpg",
        },
        {
          img: "./images/port/port_03.png",
          title: "스페이스 오디세이 2001",
          desc: "아서 C. 클라크 (Stanley Kubrick)",
          icon: "./images/member/member04.jpg",
        },
        {
          img: "./images/port/port_04.png",
          title: "1984",
          desc: "조지 오웰(George Orwell)",
          icon: "./images/member/member05.jpg",
        },
        {
          img: "./images/port/port_05.png",
          title: "듄",
          desc: "프랭크 허버트(Frank Herbert)",
          icon: "./images/member/member06.jpg",
        },
        {
          img: "./images/port/port_06.png",
          title: "11/22/63",
          desc: "스티븐 킹(Stephen King)",
          icon: "./images/member/member07.jpg",
        },
      ],
    };
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
          border: 1px solid #000;
          display: inline-block;
          padding: 5px 20px;
          margin: 0 5px;
          border-radius: 40px;
        }
        &.active {
          a {
            color: #fff;
            background-color: #6dc9ff;
          }
        }
        &:hover {
          a {
            color: #fff;
            background-color: #6dc9ff;
          }
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
