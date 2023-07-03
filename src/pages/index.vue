<template>
  <div class="top">
    <div class="top__kv kvSec">
      <img src="" alt="" class="kvSec__img" />
    </div>

    <section class="top__pickup pickupSec">
      <h2 class="pickupSec__title secTitle">Pickup</h2>
      <carousel
        class="pickupSec__list"
        :per-page="3.6"
        :loop="true"
        :center="true"
        :show-dots="false"
      >
        <slide class="pickupSec__item slide">
          <img src="" alt="" class="pickupSec__itemImg" />
        </slide>
        <slide class="pickupSec__item slide">
          <img src="" alt="" class="pickupSec__itemImg" />
        </slide>
        <slide class="pickupSec__item slide">
          <img src="" alt="" class="pickupSec__itemImg" />
        </slide>
        <slide class="pickupSec__item slide">
          <img src="" alt="" class="pickupSec__itemImg" />
        </slide>
        <slide class="pickupSec__item slide">
          <img src="" alt="" class="pickupSec__itemImg" />
        </slide>
      </carousel>
    </section>

    <section class="top__feature featureSec">
      <h2 class="featureSec__title secTitle">Feature</h2>
      <ul class="featureSec__list">
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
        <li class="featureSec__item">
          <img src="" alt="" class="featureSec__itemImg" />
          <div class="featureSec__textBox">
            <p class="featureSec__itemCat">category</p>
            <h3 class="featureSec__itemTitle">
              テキストテキストテキストテキストテキストテキストテキストテキスト
            </h3>
            <time class="featureSec__itemDate" datetime="2023-07-01"
              >2023.07.01</time
            >
          </div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import Carousel from 'vue-carousel/src/Carousel.vue'
import Slide from 'vue-carousel/src/Slide.vue'

export default {
  name: 'IndexPage',
  components: {
    Carousel,
    Slide,
  },
}
</script>

<style lang="scss">
.secTitle {
  text-align: center;
  text-transform: uppercase;
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 40px;
}
</style>

<style lang="scss" scoped>
.kvSec {
  width: 100%;
  height: 600px;
  margin-bottom: 110px;

  &__img {
    width: 100%;
    height: 100%;
    background-color: blue;
  }
}

.secTitle {
  text-align: center;
  text-transform: uppercase;
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 40px;
}
.pickupSec {
  margin-bottom: 110px;

  &__itemImg {
    width: 360px;
    height: 240px;
    background-color: #ff0000;
  }
}

.featureSec {
  padding-bottom: 60px;

  &__list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    place-items: center;
    gap: 26px;
    // width: 1210px;
    width: fit-content;
    margin: 0 auto;
    word-break: break-word;
  }

  &__item {
    width: 360px;
    // filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
    box-shadow: 0px 0px 8px #00000029;
    // border: 1px solid #cccccc;
  }

  &__itemImg {
    width: 385px;
    height: 257px;
    background-color: #ff0000;
  }

  &__textBox {
    padding: 30px 33px;
  }

  &__itemCat {
    font-size: 12px;
  }

  &__itemTitle {
    font-size: 15px;
    font-weight: normal;
    padding: 24px 0 41px;
  }

  &__itemDate {
    display: block;
    font-size: 12px;
    color: #999999;
    text-align: right;
  }
}
</style>
