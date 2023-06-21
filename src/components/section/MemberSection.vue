<template>
  <section id="memberSection" class="member__wrap section center">
    <h3>SF 장르 작가 & 영화감독 소개</h3>
    <p>SF에서 유명한 작가와 감독들을 소개합니다.</p>
    <div class="member__inner container">
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/member01.jpg" alt="작가" />
        </figure>
        <div class="member_body">
          <h4>아이작 아시모프 (Isaac Asimov)</h4>
          <a href="#" class="btn">작품 보기</a>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/member02.jpg" alt="작가" />
        </figure>
        <div class="member_body">
          <h4>필립 K. 딕 (Philip K. Dick):</h4>
          <a href="#" class="btn">작품 보기</a>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/member03.jpg" alt="감독" />
        </figure>
        <div class="member_body">
          <h4>스탠리 큐브릭 (Stanley Kubrick)</h4>
          <a href="#" class="btn">작품 보기</a>
        </div>
      </div>
    </div>
  </section>
</template>
<style lang="scss">
// member__wrap
.member__wrap {
}
.member__inner {
  @include flex-between;

  .member {
    width: 32%;
    border: 2px solid var(--color_body);

    .member__header {
      margin-top: -20px;
      padding: 20px;

      img {
        width: 100%;
      }
    }
    .member_body {
      margin-top: -90px;
      padding: 15px 10px;
      background: #000;
      color: #fff;
      z-index: 100;
      position: relative;

      h4 {
        font-size: 22px;
      }

      a {
        color: #fff;
        text-decoration: underline;
        text-underline-position: under;
      }
    }
  }
}
</style>
