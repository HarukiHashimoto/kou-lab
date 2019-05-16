<template>
  <v-container fluid grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card flat class="about">
          <v-card-title primary-title>
              <div class="display-1 font-weight-bold title-eng">About</div>
              <div class="descript"><span class="grey--text">「耕らぼ」について</span></div>
          </v-card-title>
          <v-card-text class="card-text">
            「農」と「食」に関わる活動に取組み、<br/>「食」を豊かに、「心」を豊かにします。<br/><br/>
            <ul type="square">
              <li>安全で美味しい『食』を提供するため、私たちは常に努力・探求し続けます。</li>
              <li>野菜づくりは土づくり、人づくり。自然に感謝し、常に人に感謝の心を持って活動します。</li>
            </ul>
          </v-card-text>
        </v-card>
      </v-flex>
      <v-flex xs12>
        <v-card flat class="service">
          <v-card-title primary-title>
              <div class="display-1 font-weight-bold title-eng">Service and Style</div>
              <div class="descript"><span class="grey--text">事業内容<span class="desc-devide">|</span>活動スタイル</span></div>
          </v-card-title>
          <v-layout wrap>
            <v-flex xs12 sm6>
              <v-card flat>
                <v-img :src="require('@/assets/salad.jpg')"></v-img>
                <v-card-title primary-title>
                    <div class="headline font-weight-bold">サービス</div>
                </v-card-title>
                <v-card-text class="card-text">
                  お客様の顔が見える販売。
                  直営直売を主とし、関連直売所及び、個人・お昼休み訪問販売なども承ります。
                </v-card-text>
              </v-card>
            </v-flex>
            <v-flex xs12 sm6>
              <v-card flat>
                <v-img :src="require('@/assets/saibai-s.jpg')"></v-img>
                <v-card-title primary-title>
                    <div class="headline font-weight-bold">栽培</div>
                </v-card-title>
                <v-card-text class="card-text">
                  「施設園芸栽培及び、季節露地栽培をしています。
                  減農薬で安全かつ美味しいお野菜を，栄養価が高く安定した品質で提供いたします。
                  食卓を彩る、新鮮で鮮やかな野菜たちです。
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-card>
      </v-flex>
      <farm></farm>
      <contact></contact>
    </v-layout>
  </v-container>
</template>

<script>
import farm from '@/components/Farm.vue'
import contact from '@/components/Contact.vue'

export default {
  components:{
    farm,
    contact
  }
}
</script>

<style>
  @media screen and (max-width:480px){
    .container {
      padding: 0;
    }
  }
  .title-eng {
    margin-right: 10px;
  }

  .desc-devide {
    margin-left: 10px;
    margin-right: 10px;
  }

  /* スマホ横以上 */
  @media screen and (min-width: 481px) {
    .title-eng {
      margin-right: 20px;
    }
  }

</style>
