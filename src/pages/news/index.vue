<template>
  <div class="news">
    <section class="news__feature featureSec">
      <h2 class="featureSec__title secTitle">お知らせ一覧</h2>
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
export default {
  name: 'postsIndexPage',
}
</script>

<style lang="scss" scoped>
.featureSec {
  margin-top: 100px;
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
