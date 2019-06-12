<template>
  <v-flex xs12>
    <v-card flat class="product">
      <v-card-title primary-title>
          <div class="display-1 font-weight-bold title-eng">Products</div>
          <div class="descript"><span class="grey--text">栽培品目</span></div>
      </v-card-title>
      <v-img :src="require('@/static/yasai.png')"></v-img>
      <v-layout wrap justify-center>
        <template v-for="item of items">
          <v-flex xs12 sm4>
            <v-card hover height="160px">
              <v-card-title primary-title>
                  <span class="font-weight-bold">{{ item.name }}</span>
              </v-card-title>
              <v-card-text class="card-text">
                {{ item.desc }}
              </v-card-text>
            </v-card>
          </v-flex>
        </template>
      </v-layout>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: '果菜類',
          desc: 'トマト、ナス、キュウリ、オクラ、ズッキーニ、ピーマン、パプリカ、トウガラシ、カボチャ'
        },
        {
          name: '葉菜類',
          desc: 'キャベツ、レタス、ホウレンソウ、コマツナ、ハクサイ、ミズナ、シュンギク、ミニチンゲンサイ、ニラ'
        },
        {
          name: '茎菜類',
          desc: 'アスパラガス、タマネギ、ネギ、ニンニク'
        },
        {
          name: '根菜類',
          desc: 'ダイコン、ニンジン、カブ、ショウガ、ゴボウ'
        },
        {
          name: '花菜類',
          desc: '茎ブロッコリー、カリフラワー'
        },
        {
          name: 'イモ類',
          desc: 'サツマイモ、ジャガイモ、サトイモ'
        },
        {
          name: 'マメ類',
          desc: '枝豆、スナップエンドウ、ソラマメ、インゲン'
        },    
        {
          name: '果樹類',
          desc: 'カキ、クリ、イチジク、イチゴ、ブドウ'
        }
      ]
    }
  }
}
</script>

<style>

</style>
