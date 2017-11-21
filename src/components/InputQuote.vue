<template>
  <div class="row">
      <div class="col-md-6 col-md-offset-3">
          <div class="row">
              <div class="col-md-12">
                  <h3>Quote</h3>
                  <div class="input-group">
                    <textarea v-model='quote' cols="70" rows="5"></textarea> 
                  </div>
              </div>
              <div class="col-md-12 text-center">
                  <button class="btn btn-primary" @click="submitQuote">Add Quote</button>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import { quoteBus } from '../main'

export default {
   
    data: ()=>{
        return {
            quote : ''
        }
    },
    methods: {
        submitQuote(){
            quoteBus.$emit('newQuoteAdded', this.quote)
            this.quote = ''
        }
    }
}
</script>

<style>

</style>
