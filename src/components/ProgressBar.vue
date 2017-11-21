<template>
  <div class="row">
      <div class="col-md-3">
          <h2>Quotes Added</h2>
      </div>
      <div class="col-md-12">
          <div class="back">
              <div class="blue" :style="{'width': width + '%'}">
                 <p>{{width / 10}}/10</p>
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
            width: 0
        }
    },
    methods:{
        newQuote(){
            this.width += 10;
        }
    },
    created(){
        quoteBus.$on('newQuoteAdded', (data)=>{
            if(this.width <100)
            this.newQuote()
        })

        quoteBus.$on('quoteRemoved', (data) =>{
            this.width -=10
        })
    }
}
</script>

<style scoped>
    .back{
        height: 30px;
        background: #ccc;
        border-radius: 5px;
    }
    .blue{
        height: 30px;
        background: darkblue;
        border-radius: 5px;
        text-align: center;
        transition: width 300ms;
    }
    p{
        color:white;
    }
</style>
