<template>
  <div class="contact">

    <h2>Contact</h2>

    <div class="container">
      <form action="action_page.php">

        <div class="inputs">
          <input type="text" id="fname" name="firstname" placeholder="Your name..">
          <input type="text" id="lname" name="lastname" placeholder="Your last name..">
          <input type="text" id="email" name="email" placeholder="Your email..">
        </div>


        <textarea id="subject" name="subject" placeholder="Write something.." style="height:200px"></textarea>

        <div class="check">
            <input type="checkbox" @change="displayCode()">
            <p>By checking this case, you accept the legal notices of Netflix for art </p>
        </div>

        <button>Envoyer</button>
      </form>
    </div>

    <div class="contactFooter">
      <div>
        <i class="fab fa-twitter"></i>


      </div>
      <div>
        <p>Terms of use</p>
        <p>Contact</p>
      </div>

    </div>
  </div>

</template>

<script>
// @ is an alias to /src

export default {
  name: 'Contact',
  components: {

  },
  methods:{
    displayCode: function (){
      if(document.querySelector("input[type=checkbox]").checked === true){
        document.querySelector("button").textContent = "2659"
      }else{
        document.querySelector("button").textContent = "Envoyer"

      }
    }
  }
}
</script>
<style>
.contactFooter{
  height: 7vh;
  background-color: #232F3E;
  position: absolute;
  bottom: 0;
  width: 100%;
  color: white;
  padding: 10px 100px 10px 100px;
  display: flex;
  justify-content: space-between;
}
.contactFooter>div{
  display: flex;
  align-items: center;
}
.contactFooter p{
  margin-top: 0 !important;
  margin-bottom: 0 !important;
  margin-left: 50px;
}
input[type=text], select, textarea {
  width: 40%; /* Full width */
  padding: 12px; /* Some padding */
  border: 1px solid #ccc; /* Gray border */
  border-radius: 4px; /* Rounded borders */
  box-sizing: border-box; /* Make sure that padding and width stays in place */
  margin-top: 6px; /* Add a top margin */
  margin-bottom: 30px; /* Bottom margin */
  resize: vertical /* Allow the user to vertically resize the textarea (not horizontally) */
}

/* Style the submit button with a specific background color etc */
input[type=submit] {
  background-color: #04AA6D;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

/* When moving the mouse over the submit button, add a darker green color */
input[type=submit]:hover {
  background-color: #45a049;
}

/* Add a background color and some padding around the form */
.container {
  border-radius: 5px;
  padding: 20px;
  display: flex;
  justify-content: center;
}
.container .inputs {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.container form {
  text-align: center;
}
.check{
  display: flex;
  align-items: baseline;
}
.check input{
  margin-right: 20px;
}
.contact{
  margin-top: 7vh;
}
textarea{
  margin-top: 30px !important;
  width: 100% !important;
  margin-bottom: 10px !important;
}
button{
  background-color: #FF9A00;
  border: none;
  border-radius: 50px !important;
  color: white;
  padding: 10px 20px 10px 20px;
  margin-top: 20px !important;
}
</style>