<template>
  <div class="about">

    <p>Remplissez le carré blanc</p>

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
      code : 1234,
      displayCode : false,
      range : 0,
      cssProperty : 'background : linear-gradient(90deg, rgb(0, 204, 203)' + this.range + '%, transparent ' + this.range + '%)'
    };
  },
  name: 'Home',
  components: {
    Code,
  },
  methods:{

    updateRange : function () {
      this.range = document.querySelector("input").value
      this.cssProperty = 'background : linear-gradient(90deg, rgb(0, 204, 203)' + this.range + '%, transparent ' + this.range + '%)'
      document.querySelector(".drawing").style.backgroundImage = this.cssProperty
    console.log(this.range)

      if(this.range > 99){
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
}

input{
  width: 50% !important;
}
</style>