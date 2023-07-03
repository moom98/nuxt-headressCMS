<template>
  <footer class="footer">
    <h1 class="footer__title secTitle">contact</h1>
    <div class="footer__inner">
      <div class="footer__textBox">
        <p class="footer__text">テキストテキストテキスト</p>
        <p class="footer__text">
          テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキ
          ストテキストテキストテキストテキストテキストテキストテキストテキスト
        </p>
        <p class="footer__text">
          テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキ
          ストテキストテキストテキストテキストテキストテキストテキストテキスト
        </p>
      </div>
      <div class="footer__textBox">
        <p class="footer__text">テキストテキストテキスト</p>
        <p class="footer__text">
          テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキ
          ストテキストテキストテキストテキストテキストテキストテキストテキスト
        </p>
        <p class="footer__text">
          テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキ
          ストテキストテキストテキストテキストテキストテキストテキストテキスト
        </p>
      </div>
    </div>
    <div class="footer__copy">&copy; maigo</div>
  </footer>
</template>

<script>
export default {
  name: 'LayoutFooter',
}
</script>

<style lang="scss" scoped>
.footer {
  width: 100%;
  padding: 66px 0 12px 0;
  background-color: $mainColor;
  color: white;

  // &__title {
  //   text-align: center;
  //   text-transform: uppercase;
  // }

  &__inner {
    display: flex;
    justify-content: center;
    gap: 140px;
  }

  &__textBox {
    width: 570px;
  }

  &__copy {
    margin-top: 64px;
    font-size: 12px;
    text-align: center;
  }
}
</style>
