<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

  <div id="nav">

    <div>
      <router-link to="/">
        <img src="https://cdn.discordapp.com/attachments/897418959454879744/897746838277484544/amazone_logo_blanc.png" alt="">
      </router-link>

    </div>
    <router-link class="lastClue" to="/">Corrigez l'erreur dans le nombre d'articles...</router-link>

    <div class="menus">

      <router-link to="/contact">Contact</router-link>
    </div>

  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  background-color: #232F3E;
  padding: 0px 100px 0px 100px;
  height: 8vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}
#nav img{
  width: 100px;
  background-position: bottom;
}

#nav .menus a {
  color: white;
  text-decoration: none;
  padding-left: 40px;
}
.lastClue{
  color: #232F3E !important;
  text-decoration: none;
  font-size: 12px;

}
.lastClue:hover{
  color: white !important;
  transition: 2s ease all;
}
</style>
