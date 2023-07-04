<template>
  <header id="header" class="header">
    <nuxt-link to="/" href="" class="header__link">
      <h1 class="header__title">Maigo</h1>
    </nuxt-link>
    <button id="navBtn" class="header__button" @click="navToggle">
      <span class="header__button-top"></span>
      <span class="header__button-middle"></span>
      <span class="header__button-bottom"></span>
    </button>

    <nav id="gnav" class="gnav">
      <ul class="gnav__list">
        <li v-for="(item, index) in links" :key="index" class="gnav__item">
          <a :href="item.path" class="gnav__link" @click="handleLinkClick(item)"
            >{{ item.label }}
          </a>
        </li>
      </ul>
    </nav>

    <div id="mask" class="mask" @click="navClose"></div>
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

  methods: {
    navToggle() {
      const header = document.querySelector('#header')
      header.classList.toggle('is-active')
    },

    navClose() {
      const header = document.querySelector('#header')
      header.classList.remove('is-active')
    },

    handleLinkClick(item) {
      this.navClose()
      // メソッドを実行して遷移先のURLにリダイレクト
      this.$router.push(item.path)
    },
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
  padding: 20px 40px;

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
    position: relative;
    z-index: 20;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px;
    background-color: transparent;
    border: none;
    cursor: pointer;

    .header.is-active & {
      .header__button-top {
        transform: translateY(10px) rotate(315deg);
        background-color: #fff;
      }
      .header__button-middle {
        opacity: 0;
      }
      .header__button-bottom {
        transform: translateY(-10px) rotate(-315deg);
        background-color: #fff;
      }
    }
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

.mask {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #000;
  opacity: 0.8;
  z-index: 10;
  cursor: pointer;

  .header.is-active & {
    display: block;
  }
}

.gnav {
  position: fixed;
  top: 0;
  left: -300px;
  z-index: 20;
  opacity: 0;
  width: 300px;
  height: 100vh;
  padding: 60px 25px;
  color: #fff;
  background-color: #121212;
  transition: all 0.5s ease;

  .header.is-active & {
    left: 0;
    opacity: 1;
  }

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
