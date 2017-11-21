<template>
  <div class="col-sm-3" @click="deleteme">
      <slot></slot>
  </div>
</template>

<script>
import { quoteBus } from '../main'

export default {
    props:{
        index: Number
    },
    methods:{
        deleteme(){
            this.$emit('quoteDeleted', this.index)
            quoteBus.$emit('quoteRemoved', this.index)
        }
    }
}
</script>

<style scoped>
    div{
        box-shadow: 1px 1px 2px #aaaaaa;
        padding: 20px;
        margin: 20px 10px ;
    }
    h4{
        font-style: italic;
    }
</style>
