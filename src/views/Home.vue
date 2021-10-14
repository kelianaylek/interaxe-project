<template>
  <div class="home">

    <p>Bienvenue dans le monde de <span>Jean Beseausse</span>
      <br>
      plus de <input @change="lastClue()" type="text" :value="itemNumber">produits sont disponibles dès <span>maintenant</span>
    </p>


    <div class="lastCode" v-if="itemNumber == 9">
      9217
    </div>


    <div class="input">
      <input type="text" placeholder="Tu as besoin de quoi ?" >
      <button @click="firstClue()">Rechercher</button>
    </div>


    <div>
      <p>Découvrir</p>
    </div>
  </div>

  <div class="articles">
    <Articles></Articles>
  </div>


</template>

<script>
// @ is an alias to /src
import Articles from "@/components/Articles";
export default {
  name: 'Home',
  components: {
    Articles
  },
  data: function() {
    return {
      displayCode: false,
      itemNumber : 10,
    };
  },
  methods:{
    firstClue: function (){
      if(document.querySelector("input").value === 'indice'){
        document.querySelector("input").value = "7602"
      }
    },
    lastClue: function (){
      this.itemNumber = document.querySelector("p>input").value
    },
  },

}
</script>
<style>
.home>p>input{
  border: none;
  width: 80px;
  background-color: transparent;
  color: white;
}
.home{
  height: 92vh;
  background-image: url("https://cdn.discordapp.com/attachments/784065465168691243/897787120998039613/unknown.png");
  background-position: center;
  padding-top: 15vh;
}
.home>p{
  color: white;
  font-size: 50px;
  margin-bottom: 10vh;
}
.home p span{
  font-weight: bold;
}
.home .input input, .home button{
  padding: 15px 30px 15px 30px;
  border: none;
  outline: none;
}
.home button{
  color: white;
}
.home .input input{
  border-radius: 50px;
  width: 50%;
}
.home button{
  border-radius: 50px;
  background-color: #FF9A00;
  margin-left: -50px;
}
.home .input{
  margin-bottom: 35vh;

}
.home>div>p{
  color: white;
  font-size: 20px;
}
.articles{
  height: 100vh;
  background-color: #232F3E;

}
.lastCode{
  color: #FF9A00;
  font-size: 20px;
}
</style>