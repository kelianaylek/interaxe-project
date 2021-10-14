<template>

  <div class="product">

    <h1>Panier</h1>

    <div class="flex">
      <img :src="this.image" alt="">
      <div>
        <h3>{{ this.name }}</h3>
        <p>{{ this.desc }}</p>
       <p>{{ this.price }}$</p>
      </div>
    </div>


    <div class="flex-price">
      <p>Total : {{ this.price }}$</p>
      <Button>
        <router-link :to="{ name: 'cart', params: { name: this.name , desc: this.desc, price: this.price, image: this.image }}">
          Acheter
        </router-link>
      </Button>

    </div>



  </div>


</template>

<script>

export default {
  name: 'Product',
  components: {

  },
  props: ['name', 'desc', 'price', 'image']
}
</script>
<style>
h1{
  padding-top: 10vh;
  text-align: start;
  margin-left: 200px;
}
.product{
  color: black;
}
.flex{
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: start;
}
img{
  width: 15%;
}
.flex-price{
  display: flex;
  justify-content: flex-end;
  margin-right: 200px;
  align-items: baseline;
  margin-top: 10vh;
}
.flex-price p {
  margin-right: 200px;
}
button{
  border-radius: 50px !important;
  background-color: #FF9A00;
  margin-left: -50px;
  border: none;
  text-decoration: none;
  padding: 10px 20px 10px 20px;
}

</style>