<template>
  <div class="page-wrapper">
    <div class="container w-container">
      <BlockInfo :block="blockDetail" :block_id="$route.params.block_id" />
      <Transactions :transactions="blockDetail.transactions" />
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
import BlockInfo from './components/BlockInfo'
import Transactions from './components/Transactions'

export default {
  name: 'block-detail',
  methods: {
    ...mapActions(['fetchBlockDetail'])
  },
  computed: {
    ...mapGetters(['blockDetail'])
  },
  components: {
    BlockInfo,
    Transactions
  },
  created () {
    this.fetchBlockDetail(this.$route.params.block_id)
  }
}
</script>

<style>

</style>
