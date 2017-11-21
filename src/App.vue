<template>
<div class="container">
    <my-progress-bar></my-progress-bar>
    <my-input-quote></my-input-quote>
    <my-holder></my-holder>
    <div class="row">
      <div class="col-md-12 info">
        <h4 class="text-center"> Info: Click on the Quote to delete it</h4>
      </div>
    </div>
</div>

</template>

<script>
import ProgressBar from './components/ProgressBar.vue'
import InputQuote from './components/InputQuote.vue'
import QuoteHolder from './components/QuoteHolder.vue'
  export default {
    components:{
      'my-progress-bar': ProgressBar,
      'my-input-quote': InputQuote,
      'my-holder' : QuoteHolder
    }
  }
</script>

<style scoped>
  .info{
    margin-top:50px;
    background: lightgreen;
    padding: 20px;
    border-radius: 5px;
  }
</style>
