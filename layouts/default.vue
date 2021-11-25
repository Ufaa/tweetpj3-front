<template>
  <div>
    <ex-header />
    <nuxt />
    <ex-footer />
  </div>
</template>

<script>
// ヘッダ＆フッタをインポート
import ExHeader from '~/components/SampleHeader.vue'
import ExFooter from '~/components/SampleFooter.vue'
//import ExSideber from '~/components/Sidever2.vue'

export default {
  name: 'sample',	// テンプレート名
  components: {
    ExHeader,		// <ex-header>に対応
    ExFooter,		// <ex-footer>に対応
  //  ExSideber,
  }
}
</script>