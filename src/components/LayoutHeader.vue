<template>
  <header class="header">
    <nuxt-link to="/" href="" class="header__link">
      <h1 class="header__title">Maigo</h1>
    </nuxt-link>
    <button class="header__button">
      <span class="header__button-top"></span>
      <span class="header__button-middle"></span>
      <span class="header__button-bottom"></span>
    </button>

    <nav class="gnav">
      <ul class="gnav__list">
        <li v-for="(item, index) in links" :key="index" class="gnav__item">
          <nuxt-link :to="item.path" class="gnav__link"
            >{{ item.label }}
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'LayoutHeader',
  data() {
    return {
      links: [
        {
          label: 'Pick up', // リンクのラベル
          path: '/#pickup', // パス
          isExternal: false, // 外部リンクかどうか
        },
        {
          label: 'News',
          path: '/news/',
          isExternal: false,
        },
        {
          label: 'Contact',
          path: '/#contact',
          isExternal: false,
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.header {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: 0 20px 0 40px;

  &__link {
    color: $mainColor;
    text-decoration: none;
  }

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

.gnav {
  display: none;

  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  width: 300px;
  height: 100vh;
  padding: 60px 25px;
  color: #fff;
  background-color: #121212;

  &__link {
    display: block;
    padding: 20px 0;
    border-bottom: solid 1px #fff;
    color: #fff;
    text-transform: uppercase;
    text-decoration: none;

    .gnav__item:first-of-type & {
      border-top: solid 1px #fff;
    }

    &:hover {
      text-decoration: underline;
    }
  }
}
</style>
