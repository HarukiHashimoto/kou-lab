<template>
  <v-flex xs12>
    <v-card flat class="farm">
      <v-card-title primary-title>
          <div class="display-1 font-weight-bold title-eng">Farm</div>
          <div class="descript"><span class="grey--text">立地概要</span></div>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="farms"
        hide-actions
        class="elevation-1"
      >
        <template v-slot:items="props">
          <td>{{ props.item.place }}</td>
          <td class="text-xs-right">{{ props.item.environment }}</td>
          <td class="text-xs-right">{{ props.item.area }}</td>
        </template>
      </v-data-table>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "場所",
          value: "place",
          align: "left",
          sortable: false
        },
        {
          text: "栽培環境",
          value: "environment",
          align: "right",
          sortable: false
        },
        {
          text: "面積",
          value: "area",
          align: "right",
          sortable: false
        }
      ],
      farms: [
        {
          place: "福井市帆谷町1",
          environment: "ビニールハウス",
          area: "456㎡（8m × 57m）"
        },
        {
          place: "福井市帆谷町2",
          environment: "露地",
          area: "1100㎡"
        },
        {
          place: "あわら市山室",
          environment: "露地",
          area: "4000㎡"
        }
      ]
    }
  }
}

</script>
