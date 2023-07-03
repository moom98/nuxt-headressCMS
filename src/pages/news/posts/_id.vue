<template>
  <div class="contents_area">
    <h1>お知らせ詳細</h1>
    <div class="posts_content">
      {{ posts }}
      {{ newsTagLabel }}
    </div>
    <!-- <p>{{ routeParams }}</p> -->
  </div>
</template>

<script>
export default {
  async asyncData(context) {
    try {
      // WP REST APIのベースURL
      const baseUrl = context.$config.wpBaseUrl
      const routeParams = context.params.id

      const newsUrl = baseUrl + 'news/' + routeParams

      // 記事を取得
      const posts = await context.$axios.$get(newsUrl)

      // news-tagのIDを取得
      const newsTagId = posts['news-tag'][0]

      // news-tagのラベルを取得
      const newsTag = await context.$axios.$get(
        baseUrl + 'news-tag/' + newsTagId
      )

      // 記事が存在しない場合のエラーハンドリング
      if (!posts) {
        const error = new Error('記事が見つかりませんでした')
        error.statusCode = 404
        throw error
      }

      return {
        posts,
        newsTagLabel: newsTag.name, // ラベルを追加
        routeParams,
      }
    } catch (error) {
      // エラーハンドリング
      console.error(error)
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
      routeParams: null, // 新しいプロパティを追加
    }
  },
}
</script>

<style scoped>
.contents_area {
  padding: 0 50px;
}
</style>
