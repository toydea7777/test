<template lang="pug">
section
  .q-pa-sm.text-h6 즐겨찾기
  q-tree(:nodes='nodes' default-expand-all='' node-key='label')
    template(v-slot:header-option='prop')
      .row.items-center.items-center
        span {{ prop.node.label }}
          q-btn.q-ml-sm(icon="remove" dense color="red" round size="xs")
    template(v-slot:header-statistics='prop')
      .row.items-center.items-center
        .text-weight-bold {{ prop.node.label }}

</template>

<script>

import { ref } from 'vue'

export default {
  setup () {
    const nodes = ref([
      {
        label: 'FTA 현황',
        header: 'statistics',
        children: [
          { label: 'FTA 추진현황'}
        ],
      },
      {
        label: '통계서비스',
        header: 'statistics',
        children: [
          { label: '국내관세', 
            children: [ 
              { 
                label: '품목별·FTA별 관세', 
                children: [
                  { label: '품목: 쌀 외 3, 구분 2017년, FTA 한국-미국 FTA 외 1', header: 'option'},
                  { label: '품목: 전체, 구분 2018년, FTA 한국-미국 FTA 외 1', header: 'option'},
                ] 
              }
            ] 
          },
          { label: '국내수출입', 
            children: [
              { label: '품목: 오리, 기간: 1990년 ~ 2020년, 단위: $/kg, 항목: 수입액, 국가: 전체', header: 'option'},
              { label: '품목: 타조, 기간: 1990년 ~ 2020년, 단위: $/kg, 항목: 수입액, 국가: 전체', header: 'option'},
            ],
          },
          { label: '국내수급' },
          { label: '전세계 수출입' },
          { label: '전세계 수급' },
          { label: '리포팅' },

          // { label: '품목별·FTA별 관세' },
          // { label: '품목별·연도별 관세'},
          // { label: 'WTO-FTA TRQ 운용현황'}
        ]
      },
      {
        label: 'HS 도감',
        header: 'statistics',
        children: [
          { label: '품목별 도감', 
            children: [
              { label: 'AG코드: 211031005, HSK코드:0101291000, 코드명: 경주용 말', header: 'option'},
              { label: 'AG코드: 211110001, HSK코드:0106191000, 코드명: 개', header: 'option'},
            ], 
          },
          { label: '코드 조견표', }
        ],
      },
      {
        label: '참고정보',
        header: 'statistics',
        children: [
          { label: '국가정보' },
          { label: '자료실' },
          { label: '용어사전' },
          { label: '법령정보' },
          { label: '커뮤니티' },
          { label: '관련사이트' },
        ],
      },
    ])
    return {
      nodes
    }
  }
}
</script>

<style>

</style>