<template>
  <div class="row">
      <div class="col-md-12">
          <my-new-quote v-for="(quote, i) in quoteArray" :key="i" :index='i' v-on:quoteDeleted="removeQuote($event)">
              <h4>{{quote}}</h4>
          </my-new-quote>
      </div>
  </div>
</template>

<script>
import { quoteBus } from '../main'
import Quote from './Quote.vue'

export default {
     components:{
        'my-new-quote' : Quote
    },
    data: ()=>{
        return{
            quoteArray: []
        }
    },
    methods:{
        removeQuote(value){
           this.quoteArray.splice(value,1)
        }
    },
    created(){
        quoteBus.$on('newQuoteAdded', (quote)=>{
            if(this.quoteArray.length <10)
            this.quoteArray.push(quote)
        })
    }
}
</script>

<style>

</style>
