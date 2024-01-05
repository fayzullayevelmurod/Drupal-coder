<template>
  <div class="comment_container">
    <h1 class="comment_title">
    Отзывы
  </h1>
  <img src="./assets/bg_left.png" alt="" class="bg_left">
  <swiper
    :pagination="{
      type: 'fraction',
    }"
    :navigation="true"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide>
      <div class="comment">
        <div class="comment_left">
          <img src="./assets/comment_logo.svg" alt="">
          <h6>
            Команда Drupal Coder вызвала только положительные впечатления!
          </h6>
          <p>
            Нуреев Александр, менеджер проекта Winamp Russian Community
          </p>
        </div>
        <div class="line"></div>
        <div class="comment_right">
          
        </div>

      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="comment">
        <div class="comment_left">
          <img src="./assets/comment_logo.svg" alt="">
          <h6>
            Команда Drupal Coder вызвала только положительные впечатления!
          </h6>
          <p>
            Нуреев Александр, менеджер проекта Winamp Russian Community
          </p>
        </div>
        <div class="line"></div>
        <div class="comment_right">

        </div>

      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="comment">
        <div class="comment_left">
          <img src="./assets/comment_logo.svg" alt="">
          <h6>
            Команда Drupal Coder вызвала только положительные впечатления!
          </h6>
          <p>
            Нуреев Александр, менеджер проекта Winamp Russian Community
          </p>
        </div>
        <div class="line"></div>
        <div class="comment_right">

        </div>

      </div>
    </swiper-slide>
  </swiper>
  </div>
</template>
<script>
  // Import Swiper Vue.js components
  // import { Swiper, SwiperSlide } from 'swiper/vue';
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import 'swiper/css';

  import 'swiper/css/pagination';
  import 'swiper/css/navigation';
  import { Pagination, Navigation } from 'swiper/modules';

  // Import Swiper styles
  import 'swiper/css';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Pagination, Navigation],
      };
    },
  };
</script>


<style scoped>

.comment_container {
  max-width: 1440px;
  margin: 0 auto;
}
.comment_title {
  color: #050C33;
  text-align: center;
  font-family: 'Montserrat',sans-serif;
  font-size: 42px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  padding-top: 60px;
  margin-bottom: 46px;
}

.comment {
  padding: 80px 80px 88px 120px;
  margin: 0 auto;
  max-width: 980px;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.10);
  background: #FFF;
  box-shadow: 0px 4px 60px 0px rgba(161, 161, 161, 0.25);
}

.line {
  width: 10px;
  background: #000;
  opacity: 0.2;
  height: 100%;
}

.swiper-pagination-fraction {
  position: absolute;
  top: 0;
}

.comment_left h6 {
  max-width: 440px;
  margin: 41px 0 28px 0;
  color: #050C33;
  font-family: 'Montserrat',sans-serif;
  font-size: 24px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  text-decoration-line: underline;
}

.comment_left p {
  max-width: 380px;
  color: #050C33;
  font-family: 'Montserrat',sans-serif;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
}

.mySwiper {
  width: 100%;
  border: 1px solid red;
}

.bg_left {
  position: absolute;
  left: 0;
  top: 0;
}
</style>