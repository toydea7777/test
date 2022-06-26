<template lang="pug">
q-page
  .header.q-py-xl
    .row.header-menu.justify-around.items-center.q-py-sm
      .menu FTA
      .menu 품목정보
      .menu 국가 · 통계
      .menu.active 동향정보
      .menu 자료실
      .menu 알림 · 소식

  .body.q-py-lg
    .q-gutter-sm
      q-checkbox(v-model='all' label='전체' color='black')
      q-checkbox(v-model='cate' label='수출입동향' color='teal' :val="1")
      q-checkbox(v-model='cate' label='해외곡물동향' color='orange' :val="2")
      q-checkbox(v-model='cate' label='이슈분석' color='red' :val="3")
      q-checkbox(v-model='cate' label='시장분석보고서' color='cyan' :val="4")
      q-checkbox(v-model='cate' label='장기모니터링보고서' color='green' :val="5")
      q-checkbox(v-model='cate' label='카드뉴스' color='primary' :val="6")

    .search-bar.row.q-px-md.q-py-lg
    
      .row.items-center.q-mr-lg
        .label.q-mr-md(style="font-size: 1.1rem; font-weight: bold;") 검색
        q-input( outlined dense placeholder="검색어를 입력해주세요.")

      //- .row.items-center.q-mr-lg
      //-   .label.q-mr-md(style="font-size: 1.1rem; font-weight: bold;") 키워드
      //-   q-input( outlined dense placeholder="키워드를 입력해주세요.")
      
      q-btn( label="찾기"  color="grey")

    .content-wrap.q-py-lg
      q-card(v-for="info in filteredData")
        q-card-section
          .column
            .title.q-mb-md {{ info.title }}
            .content {{ info.content }}
            .row.justify-between
              .date {{ info.date }}
              .cate {{ caseStr(info.cate) }}
    
</template>

<script>
import { ref, watch } from 'vue'
import jsonData from './data.json'
export default {
  setup(props) {

    const data = ref(jsonData)
    const all = ref(false)
    const cate =  ref([ 1, 2 ])

    const filteredData = ref([])
    

    filteredData.value = data.value.filter(el => {
      return cate.value.includes(el.cate)
    })

    watch(cate, () => {
      filteredData.value = data.value.filter(el => {
        return cate.value.includes(el.cate)
      })
    })

    const caseStr = (num) => {
      let cateSrt = ''
      switch(num) {
        case 1:
          cateSrt = '수출입동향'
          break;
        case 2:
          cateSrt = '해외곡물동향'
          break;
        case 3:
          cateSrt = '이슈분석'
          break;
        case 4:
          cateSrt = '시장분석보고서'
          break;
        case 5:
          cateSrt = '장기모니터링보고서'
          break;
        case 6:
          cateSrt = '카드뉴스'
          break;
      }
      return cateSrt
    }

    return {
      all,
      cate,
      data,
      filteredData,
      caseStr,
    }
  }
}
</script>

<style lang="scss" scoped>
.q-page {
  // max-width: 1400px;
  // margin: 0px auto;
}
.header {
  background: url(https://maps.or.kr/new/fta/img/sub/sub_visual02.jpg);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  
  .header-menu {
    border-top: 1px solid #ccc;
    border-bottom: 1px solid #ccc;
    .menu { 
      font-size: 1.2rem; 
      font-weight: bold; 
      color: #d2d2d2;

      &.active {
        color: white;
        font-weight: 900;
        font-size: 1.4rem;
      }
    }
  }
  
}

.body {
  max-width: 1400px;
  margin: 0px auto;

  .search-bar {
    border-bottom: 1px solid #ccc;
  }

  .content-wrap {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 14px;

    .title { font-weight: bold; font-size: 0.9rem; height: 50px;}
    .content { color: #252525; font-size: 0.8rem; height: 100px; overflow: hidden;}
    .date { color: #818181; }
    .cate { font-weight: 500; }
  }
}
</style>