<script>
export default {
  data() {
    return {
      headerMenu: [
        {
          text: "CHARACTERS",
          link: "#",
          active: false,
        },
        {
          text: "COMICS",
          link: "#",
          active: true,
        },
        {
          text: "MOVIES",
          link: "#",
          active: false,
        },
        {
          text: "TV",
          link: "#",
          active: false,
        },
        {
          text: "GAMES",
          link: "#",
          active: false,
        },
        {
          text: "COLLECTIBLES",
          link: "#",
          active: false,
        },
        {
          text: "VIDEOS",
          link: "#",
          active: false,
        },
        {
          text: "FANS",
          link: "#",
          active: false,
        },
        {
          text: "NEWS",
          link: "#",
          active: false,
        },
        {
          text: "SHOP",
          link: "#",
          active: false,
        }
      ],
      logoDC: "dc-logo.png"
    }
  },
  methods: {
    getImagePath: function (imgUrl) {
      return new URL(imgUrl, import.meta.url).href;
    },
    changeActivePage: function (i) {
      this.headerMenu.forEach(element => element.active = false);
      this.headerMenu[i].active = true;
    }
  }
}
</script>

<template>
  <header>
    <div class="container">
      <img :src="getImagePath('./../assets/img/' + logoDC)" alt="Logo DC">
      <ul>
        <li v-for="(element, index) in headerMenu" :class="{ active: element.active }" @click="changeActivePage(index)"
          :key="index">
          <a :href="element.link">{{ element.text }}</a>
        </li>
      </ul>
    </div>
  </header>
</template>

<style lang="scss">
@use './../style/partials/variables.scss' as *;
@use './../style/partials/mixIn.scss' as *;

header {
  position: fixed;
  z-index: 100;
  top: 0;
  width: 100%;
  background-color: #fff;

  .container {
    @include center(vertical);
    height: 115px;
    justify-content: space-between;

    img {
      height: 80px;
    }

    ul {
      @include my-display-flex;
      column-gap: 25px;
      height: 100%;

      li {
        height: 100%;
        position: relative;

        a {
          display: block;
          height: 100%;
          @include center(vertical);
        }

        &.active,
        &:hover {
          a {
            color: $blue-DC;
          }

          &::after {
            display: block;
            content: "";
            width: 100%;
            height: 4px;
            background-color: $blue-DC;
            position: absolute;
            bottom: 0;
          }
        }
      }
    }
  }
}
</style>
