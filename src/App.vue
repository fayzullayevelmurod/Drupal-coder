<template>
  <div class="wrapper">
    <div class="comment_container">
      <h1 class="comment_title">
        Отзывы
      </h1>
      <img src="./assets/bg_left.png" alt="" class="bg_left">
      <div class="comment">
        <div class="comment_left">
          <swiper
            :pagination="{
              type: 'fraction',
              el: fraction
            }"
            :navigation="{
              prevEl: prev,
              nextEl: next,
            }"
            :modules="modules"
            class="mySwiper"
          >
            <swiper-slide v-for="i in comments" :key="i">
              <div class="comment_card">
                <img :src="require(`@/assets/${i.brend}`)" alt="">
                <h6>
                  {{ i.description }}
                </h6>
                <p>
                  Нуреев Александр, менеджер проекта Winamp Russian Community
                </p>
              </div>
            </swiper-slide>
          </swiper>
        </div>
  
        <div class="line"></div>
        <div class="comment_right">
          <div class="swiper_btns">
            <button ref="prev" class="swiper-button-prev">
              <img src="./assets/arrow-left.svg" alt="">
            </button>
            <div ref="fraction" class="swiper-pagination-fraction">
              <span class="">
                1
              </span>
              <span class="number_line">/</span>
              <span class="swiper-pagination-total">
                5
              </span>
            </div>
            <button ref="next" class="swiper-button-next">
              <img src="./assets/arrow-right.svg" alt="">
            </button>
          </div>
        </div>
      </div>
    </div>
  
    <section class="works_card">
      <div class="main_container">
        <h2 class="comment_title">С нами работают</h2>
        <p class="description">Десятки компаний доверяют нам самое ценное, что у них есть в интернете – свои сайты. Мы делаем всё, чтобы наше сотрудничество было долгим.</p>
        <swiper
          :slidesPerView="'auto'"
          :loop="true"
          :spaceBetween="20"
          :centeredSlides="true"
          :speed="3000"
          :autoplay="{
            delay: 0,
          }"
          :modules="modules"
          class="works_card_slider"
        >
          <swiper-slide v-for="i in 4" :key="i">
            <div class="card_content">
              <img :src="require(`@/assets/works_card_${i}.svg`)" alt="">
            </div>
          </swiper-slide>
          <swiper-slide v-for="i in 4" :key="i">
            <div class="card_content">
              <img :src="require(`@/assets/works_card_${i}.svg`)" alt="">
            </div>
          </swiper-slide>
          <swiper-slide v-for="i in 4" :key="i">
            <div class="card_content">
              <img :src="require(`@/assets/works_card_${i}.svg`)" alt="">
            </div>
          </swiper-slide>
        </swiper>
        <swiper
          :slidesPerView="'auto'"
          :loop="true"
          :centered-slides="true"
          :spaceBetween="20"
          :centeredSlides="true"
          :speed="3000"
          :autoplay="{
            delay: 0,
            reverseDirection: true,
          }"
          :modules="modules"
          class="works_card_slider"
        >
          <swiper-slide v-for="i in 4" :key="i">
            <div class="card_content">
              <img :src="require(`@/assets/works_card_${i}.svg`)" alt="">
            </div>
          </swiper-slide>
          <swiper-slide v-for="i in 4" :key="i">
            <div class="card_content">
              <img :src="require(`@/assets/works_card_${i}.svg`)" alt="">
            </div>
          </swiper-slide>
          <swiper-slide v-for="i in 4" :key="i">
            <div class="card_content">
              <img :src="require(`@/assets/works_card_${i}.svg`)" alt="">
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </section>
  </div>
</template>
<script>
  // Import Swiper Vue.js components
  // import { Swiper, SwiperSlide } from 'swiper/vue';
  import { ref } from 'vue';
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import { Autoplay, Pagination, Navigation } from 'swiper/modules';

  import 'swiper/css';
  import 'swiper/css/pagination';
  import 'swiper/css/navigation';

  // Import Swiper styles
  import 'swiper/css';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const prev = ref(null);
      const next = ref(null);
      const fraction = ref(null);
      return {
        modules: [Autoplay, Pagination, Navigation],
        prev,
        next,
        fraction
      };
    },
    data () {
      return {
        comments: [
          {
            brend: 'comment_logo.svg',
            description: 'Команда Drupal Coder вызвала только положительные впечатления!'
          },
          {
            brend: 'works_card_1.svg',
            description: 'Lorem ipsum dolor sit, amet consectetur adipisicing.'
          },
          {
            brend: 'works_card_2.svg',
            description: 'Provident similique accusantium nemo autem.'
          },
          {
            brend: 'works_card_3.svg',
            description: 'Perspiciatis minima nesciunt dolorem!'
          },
          {
            brend: 'works_card_4.svg',
            description: 'Commodi minima excepturi repudiandae velit hic maxime doloremque.'
          }
        ]
      }
    }
  };
</script>


<style>
body {
  font-family: "Montserrat", sans-serif;
  font-style: normal;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

button {
  background: transparent;
  outline: none;
  border: none;
}

.wrapper {
  width: 100%;
  overflow: hidden;
}

.main_container {
  max-width: 980px;
  margin: 0 auto;
}

.description {
  color: var(--main-black, #050C33);
  text-align: center;
  font-size: 16px;
  font-weight: 500;
  line-height: 22px;
  opacity: 0.7;
}

.works_card .description {
  max-width: 740px;
  margin: 0 auto 42px;
}

.works_card .comment_title {
  margin-bottom: 10px;
  margin-top: 160px;
}

.works_card_slider {
  overflow: visible;
  margin-bottom: 20px;
  user-select: none;
}

.works_card_slider:last-child {
  margin-bottom: 160px;
}

.works_card_slider .swiper-wrapper{
  transition-timing-function:linear;
}

.works_card_slider .swiper-slide {
  border-radius: 5px;
  border: 1px solid #E5E5E5;
  cursor: pointer;
  width: 291px;
}

.works_card_slider .swiper-slide .card_content {
  height: 155px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.swiper_btns{
  width: 206px;
  /* border: 1px solid red; */
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.swiper-pagination-fraction {
  width: auto;
  text-align: center;
}

.swiper-pagination-fraction span {
  font-family: 'Montserrat',sans-serif;
  font-size: 28px;
  font-style: normal;
  font-weight: 400;
  line-height: 28px;
}

.swiper-wrapper {
  padding: 5px;
}

/* .swiper-pagination-current {
  color: #050C33;
}

.number_line {
  color: #E0E0E0;
}

.swiper-pagination-total {
  color: #E0E0E0;
} */

.comment_right {
  display: flex;
  align-items: center;
}

.swiper-button-prev {
  position: absolute;
}

.swiper-button-prev::after {
  display: none;
}
.swiper-button-next::after {
  display: none;
}

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
  display: flex;
  max-width: 980px;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.10);
  background: #FFF;
  box-shadow: 0px 4px 60px 0px rgba(161, 161, 161, 0.25);
}

.line {
  margin: 0 60px;
  width: 1px;
  height: auto;
  background: #000;
  opacity: 0.2;
  /* height: 100%; */
}

.comment_left {
  /* padding-right: 60px; */
  width: 440px;
  position: relative;
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

.bg_left {
  position: absolute;
  left: 0;
  top: 0;
  width: 23%;
}


.swiper-pagination-fraction {
  color: #E0E0E0;
  font-family: "Montserrat", sans-serif;
  font-size: 28px;
  font-style: normal;
  font-weight: 400;
  line-height: 28px;
  display: flex;
  gap: 8px;
}

.swiper-pagination-current {
  color: #050C33;
}

@media only screen and (max-width: 992px) {
  .comment {
    padding: 30px;
    flex-direction: column;
    gap: 30px;
    margin: 0px 20px;
  }

  .main_container {
    padding: 0 20px;
  }

  .comment_title {
    margin-top: 30px;
    padding-top: 0;
    font-size: 30px;
    margin-bottom: 20px;
  }

  .comment_left {
    width: 100%;
  }

  .comment_left h6  {
    font-size: 20px;
  }

  .swiper_btns {
    margin: 0 auto;
  }

  .line {
    margin: 0;
    width: 100%;
    height: 1px;
  }

  .swiper-pagination-fraction {
    font-size: 20px;
    gap: 8px;
  }

  .swiper-pagination-fraction span {
    font-size: 20px;
  }
}
</style>