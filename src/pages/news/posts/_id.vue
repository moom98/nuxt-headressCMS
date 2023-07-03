<template>
  <div class="contents_area">
    <h1 class="title">
      {{ posts.title.rendered }}
    </h1>
    <p v-if="newsTagLabel" class="category">カテゴリー：{{ newsTagLabel }}</p>
    <p v-if="thumbnailPath"><img :src="thumbnailPath" alt="サムネイル" /></p>
    <div v-if="posts.acf.contents" class="posts_content">
      {{ posts.acf.contents }}
    </div>
    <div
      v-if="posts.acf.edit_contents"
      class="posts_content_edit"
      v-html="posts.acf.edit_contents"
    ></div>
    <!-- <div style="margin: 30px">
      {{ posts }}
    </div> -->
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

      // thumbnailのIDを取得
      const mediaId = posts.acf.thumbnail
      const mediaUrl = baseUrl + 'media/' + mediaId

      // メディア情報を取得
      const mediaInfo = await context.$axios.$get(mediaUrl)

      // 画像のURLを取得
      // const imageUrl = mediaInfo.source_url

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
        thumbnailPath: mediaInfo.source_url, // thumbnailフィールドのURLの取得
        routeParams,
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
      routeParams: null, // 新しいプロパティを追加
    }
  },
}
</script>

<style scoped>
.contents_area {
  margin: 50px 0;
  padding: 0 50px;
}

.title {
  margin-bottom: 10px;
}

.category {
  margin-bottom: 50px;
  padding-bottom: 10px;
  border-bottom: 1px solid #ccc;
}

.posts_content {
  margin: 30px 0;
}
</style>
