<template>
  <div class="contents_area">
    <h1>お知らせ詳細</h1>
    <div class="posts_content">
      {{ posts }}
    </div>
    <!-- <p>{{ routeParams }}</p> -->
  </div>
</template>

<script>
export default {
  async asyncData(context) {
    // WP REST APIのベースURL
    const baseUrl = context.$config.wpBaseUrl
    const routeParams = context.params.id

    const newsUrl = baseUrl + 'news/' + routeParams

    // 記事を取得
    const posts = await context.$axios.$get(newsUrl)

    return {
      posts,
      routeParams,
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
