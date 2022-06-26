<template lang="pug">
section


  .row.q-pt-lg
    .col(style="border-right: 1px solid #ccc;")
      .q-ml-md.q-mt-md
        .text-h6 타이포그래피
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-h1
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-secondary.q-ml-sm(role='alert') h1
          .col-sm-9.col-12.text-h1 제목 1
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-h2
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-secondary.q-ml-sm(role='alert') h2
          .col-sm-9.col-12.text-h2 제목 2
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-h3
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-secondary.q-ml-sm(role='alert') h3
          .col-sm-9.col-12.text-h3 제목 3
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-h4
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-secondary.q-ml-sm(role='alert') h4
          .col-sm-9.col-12.text-h4 제목 4
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-h5
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-secondary.q-ml-sm(role='alert') h5
          .col-sm-9.col-12.text-h5 제목 5
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-h6
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-secondary.q-ml-sm(role='alert') h6
          .col-sm-9.col-12.text-h6 제목 6
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-subtitle1
          .col-sm-9.col-12.text-subtitle1 부제목 1
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-subtitle2
          .col-sm-9.col-12.text-subtitle2 부제목 2
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-body1
          .col-sm-9.col-12.text-body1
            | 본문 내용입니다.
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-body2
          .col-sm-9.col-12.text-body2
            | 본문 내용입니다.
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-caption
          .col-sm-9.col-12.text-caption 캡션
        .row.items-center.q-mb-lg
          .col-sm-3.col-12
            .q-badge.flex.inline.items-center.no-wrap.q-badge--single-line.bg-brand-primary(role='alert') text-overline
          .col-sm-9.col-12.text-overline 오버라인
    .col
      .q-ma-md
        .text-h6 요소 간격
        .row.q-my-md.items-center
          .row(style="min-width: 90px;")
            .q-badge.q-mr-xl xs
          .text-body1 margin, padding 4px
        .row.q-my-md.items-center
          .row(style="min-width: 90px;")
            .q-badge.q-mr-xl sm
          .text-body1 margin, padding 8px
        .row.q-my-md.items-center
          .row(style="min-width: 90px;")
            .q-badge.q-mr-xl md
          .text-body1 margin, padding 16px
        .row.q-my-md.items-center
          .row(style="min-width: 90px;")
            .q-badge.q-mr-xl lg
          .text-body1 margin, padding 24px
        .row.q-my-md.items-center
          .row(style="min-width: 90px;")
            .q-badge.q-mr-xl xl
          .text-body1 margin, padding 48px
  
  .q-my-xl
    .q-ma-md
      .text-h6 반응형 브레이크 포인트
      .row.q-my-lg.items-center
        div(style="min-width:150px;")
          .q-badge.q-mr-xl 모바일 디바이스
        .text-body1 최대 599px
      .row.q-my-lg.items-center
        div(style="min-width:150px;")
          .q-badge.q-mr-xl 태블릿 및 작은화면
        .text-body1 600px ~ 1023px
      .row.q-my-lg.items-center
        div(style="min-width:150px;")
          .q-badge.q-mr-xl  나머지 화면
        .text-body1 최소 1024px

</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
