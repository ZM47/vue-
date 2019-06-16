<template>
  <div class="header">
    {{seller.description}}
    <img :src="seller.avatar" alt="" @click="showdetail">

    <detail></detail>
  </div>


</template>

<script>
  import {mapGetters} from 'vuex'
  import detail from '../detail/detail.vue'
    export default {
    created(){
      this.$store.dispatch('getSeller');
    },
      computed:mapGetters([
       'seller'
     ]),
      components:{
       detail
      },
      methods:{
      showdetail(){
        this.$store.dispatch('showDetail')
      }

      },



    }
</script>

<style scoped>
  .header {
    height: 134px;
    background-color: rgba(7, 17, 27, 0.1);
    font-size: 14px;
    color: #7e8c8d;
  }
  img{
    width: 64px;
    height:64px;
    border-radius: 2px;
  }
</style>
