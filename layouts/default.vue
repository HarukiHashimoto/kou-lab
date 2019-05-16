<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-toolbar-side-icon @click="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>{{ `chevron_${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>remove</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>
    <div id="home">
      <div class="box">
        <div class="head-text">
          <p>耕して「食」を豊かに<br/><span class="kokoro">「心」を豊かに</span></p>
        </div>
      </div>
    </div>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy;2019 耕らぼ</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '耕らぼ'
    }
  }
}
</script>

<style>
  #home {
    background-image: linear-gradient(rgba(0, 0, 0, .3), rgba(0, 0, 0, .3)), url('~@/assets/header.jpg');
    background-position: center;
    background-size: cover;
    position: relative;
    min-height: 300px;
    height: 60vw;
  }
  .box {
   position: absolute;
   width: 100%;
   text-align: center;
   bottom: 0;
  }
  .head-text {
    margin-left: 10%;
    text-align: left;
    color: #ebebeb;
    font-size: 7vw;
    font-weight: bold;
    text-shadow: 0 0 5px #383838;
  }

  span.kokoro {
    margin-left: calc(3*7vw);
  }

  /* スマホ横 */
  @media screen and (min-width: 481px) {
    .head-text {
      font-size: 5vw;
    }
    span.kokoro {
      margin-left: calc(3*5vw);
    }
  }

  /* タブレット縦以上 */
  @media screen and (min-width: 769px) {
    .head-text {
      font-size: 6vw;
    }
    span.kokoro {
      margin-left: calc(3*6vw);
    }
  }
  /* ブラウザ */
  @media screen and (min-width: 1025px) {
    .head-text {
      font-size: 61.44px;
    }
    span.kokoro {
      margin-left: calc(3*61.44px);
    }
  }
</style>
