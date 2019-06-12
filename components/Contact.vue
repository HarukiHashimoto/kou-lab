<template>
  <v-flex xs12>
    <v-card flat class="contact">
      <v-card-text class="text-xs-center display-1 font-weight-bold">
        <div class="contact-text">
          <br/>
          「食」を豊かに。「心」を豊かに。
        </div>
      </v-card-text>
      <v-layout justify-center>
        <v-flex xs10 sm7 md6 lg5 xl4 text-xs-center>
          <form method="POST" name="contact" netlify>
          <v-text-field
            label="氏名"
            solo
            background-color="#ebebeb"
            name="name"
          ></v-text-field>
          <v-text-field
            label="メールアドレス"
            solo
            background-color="#ebebeb"
            name="email"
          ></v-text-field>
          <v-text-field
            label="お問い合わせタイトル"
            solo
            background-color="#ebebeb"
            name="title"
          ></v-text-field>
          <v-textarea
            label="お問い合わせ内容"
            solo
            background-color="#ebebeb"
            name="text"
          ></v-textarea>
          <v-btn type="submit" color="teal" class="white--text font-weight-bold" block large>メール作成</v-btn>
        </form>
        </v-flex>
      </v-layout>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      title: '',
      content: ''
    }
  }
}
</script>

<style>
  .contact {
    background-image: linear-gradient(rgba(0, 0, 0, .5), rgba(0, 0, 0, .5)), url('~@/static/contact.jpg');
    background-position: center;
    background-size: cover;
    position: relative;
    min-height: 300px;
    height: 600px;
  }
  .contact-text {
    color: #ebebeb;
    font-weight: bold;
    font-size: 18px;
  }
  /* スマホ横 */
  @media screen and (min-width: 481px) {
    .contact-text {
      font-size: 28px;
    }
  }
  /* タブレット縦以上 */
  @media screen and (min-width: 769px) {
    .contact-text {
      font-size: 30px;
    }
  }
  /* ブラウザ */
  @media screen and (min-width: 1025px) {
  }
</style>
