<template>
  <v-app>
    <v-toolbar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-toolbar-title v-text="title" @click="$vuetify.goTo('#app')"/>
      <v-spacer />
      <div class="text-xs-center">
        <v-btn color="teal" class="white--text email-btn-text" @click="$vuetify.goTo('.contact')">
          お問い合わせ
          <v-icon light right>email</v-icon>
        </v-btn>
      </div>
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
      <span>&copy;2019- KOU LAB</span>
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
