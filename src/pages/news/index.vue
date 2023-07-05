<template>
  <div class="news">
    <section class="news__feature featureSec">
      <h2 class="featureSec__title secTitle">ALL FEATURE</h2>
      <ul class="featureSec__list">
        <li
          v-for="(post, index) in posts"
          :key="index"
          class="featureSec__item"
        >
          <nuxt-link :to="'/news/posts/' + post.id" class="featureSec__link">
            <img
              :src="post.acf.thumbnail.url"
              alt=""
              class="featureSec__itemImg"
            />
            <div class="featureSec__textBox">
              <p class="featureSec__itemCat">category</p>
              <h3 class="featureSec__itemTitle">
                テキストテキストテキストテキストテキストテキストテキストテキスト
              </h3>
              <time class="featureSec__itemDate" datetime="2023-07-01"
                >2023.07.01</time
              >
            </div>
          </nuxt-link>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: 'NewsArchive',

  async asyncData(context) {
    try {
      // WP REST APIのベースURL
      const baseUrl = context.$config.wpBaseUrl

      const newsUrl = baseUrl + 'news/'

      // 記事を取得
      const posts = await context.$axios.$get(newsUrl)

      // 記事が存在しない場合のエラーハンドリング
      if (!posts) {
        const error = new Error('記事が見つかりませんでした')
        error.statusCode = 404
        throw error
      }

      return {
        posts,
      }
    } catch (error) {
      // エラーハンドリング
      // console.error(error)
      // 404エラーの場合はエラーページにリダイレクトする
      if (error.statusCode === 404) {
        context.error({
          statusCode: 404,
          message: '記事が見つかりませんでした',
        })
      }
      throw error
    }
  },
  data() {
    return {
      posts: [],
    }
  },
}
</script>

<style lang="scss" scoped>
.featureSec {
  margin-top: 100px;
  padding: 0 30px 60px;

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

  &__link {
    color: $mainColor;
    text-decoration: none;

    &:hover {
      text-decoration: underline;
    }
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
