<template>
  <div class="about">

    <p>Faites un dégradé</p>

    <div  v-bind:style="cssProperty"  class="drawing">
    </div>

    <input type="range" v-model="range" @change="updateRange(range)" class="form-range" min="0" max="100" id="customRange1">

    <Code :displayCode="displayCode" :code="code"></Code>

  </div>
</template>

<script>
// @ is an alias to /src
import Code from '@/components/Code.vue'

export default {
  data: function() {
    return {
      code : 4567,
      displayCode : false,
      range : 100,
      cssProperty : 'background : linear-gradient(90deg, rgb(0, 204, 203)' + 0 + '%, transparent ' + 100 + '%)'
    };
  },
  name: 'Home',
  components: {
    Code,
  },
  methods:{

    updateRange : function () {
      this.range = document.querySelector("input").value
      this.cssProperty = 'background : linear-gradient(90deg, rgb(0, 204, 203)' + 0 + '%, transparent ' + 100 + '%)'
      document.querySelector(".drawing").style.backgroundImage = this.cssProperty
      console.log(this.range)

      if(this.range < 1){
        this.displayCode = true
      }else{
        this.displayCode = false

      }
    }
  },
  updated() {
    this.updateRange()
  }
}
</script>
<style>

.drawing{
  width: 200px;
  height: 150px;
  border: 1px black solid;
  margin: 0 auto;
  margin-bottom: 50px;
  margin-top: 50px;
  background : linear-gradient(90deg, rgb(0, 204, 203) 100%, transparent 100%)
}

input{
  width: 50% !important;
}
</style>