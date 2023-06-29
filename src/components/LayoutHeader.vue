<template>
  <header class="header">
    <h1 class="header__title">Maigo</h1>
    <button class="header__button">
      <span class="header__button-top"></span>
      <span class="header__button-middle"></span>
      <span class="header__button-bottom"></span>
    </button>
  </header>
</template>

<script>
export default {
  name: 'LayoutHeader',
}
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: $contentWidth;

  &__title {
    font-size: 35px;
    font-weight: 700;
  }

  &__button {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 10px;
    background-color: transparent;
    border: none;
    cursor: pointer;
  }

  &__button-top,
  &__button-middle,
  &__button-bottom {
    display: block;
    width: 30px;
    height: 2px;
    background-color: $mainColor;
    transition: transform 0.3s ease;
  }
}
</style>
