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
            <span class="featureSec__photo">
              <img
                :src="post.acf.thumbnail.url"
                alt=""
                class="featureSec__itemImg"
              />
            </span>
            <div class="featureSec__textBox">
              <p class="featureSec__itemCat">{{ newsTagLabel[index] }}</p>
              <h3 class="featureSec__itemTitle">
                {{ post.acf.contents }}
              </h3>
              <time class="featureSec__itemDate" datetime="2023-07-01">{{
                post.date
              }}</time>
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
      const tagLabel = []

      posts.forEach((post) => {
        const newsTagId = post['news-tag'][0]
        const newsTag = context.$axios.$get(baseUrl + 'news-tag/' + newsTagId)
        newsTag
          .then((result) => {
            // console.log(result.name)
            tagLabel.push(result.name)
          })
          .catch((error) => {
            console.error(error)
          })
      })

      // 記事が存在しない場合のエラーハンドリング
      if (!posts) {
        const error = new Error('記事が見つかりませんでした')
        error.statusCode = 404
        throw error
      }

      return {
        posts,
        newsTagLabel: tagLabel, // ラベルを追加
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
    grid-template-columns: repeat(2, 1fr);
    place-items: top;
    flex-wrap: wrap;
    width: 100%;
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

  &__photo {
    display: block;
    width: 100%;
    height: 0;
    padding-bottom: 56%;
    position: relative;
    overflow: hidden;
  }

  &__itemImg {
    display: block;
    width: 100%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    /* width: 385px;
    height: 257px; */
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
