
<template>
    <div>
 <v-stepper v-model="numStep">
     <v-stepper-header>
                <v-stepper-step :complete="numStep > 1" step="1">
                    Step1
                </v-stepper-step>
                 <v-divider></v-divider>
                <v-stepper-step :complete="numStep > 2" step="2">
                    Step2
                </v-stepper-step>
                 <v-divider></v-divider>
                <v-stepper-step :complete="numStep > 3" step="3">
                    Step3
                </v-stepper-step>
    </v-stepper-header>
      <v-stepper-items>

        <v-stepper-content step="1">   
     <form>
         <div class="container">
        <h1>Register</h1>
        <p>Please fill in this form to create an account.</p>
        <hr>
          <label for="email"><b>Email</b></label>
          <input v-model ="email" type="text" placeholder="Enter Email" name="email" required>
          <label for="name"><b>Name</b></label>
          <input v-model="name" type="text" placeholder="Enter Name" name="name" required>
          <label for="surname"><b>Surname</b></label>
          <input v-model="surname" type="text" placeholder="Enter Surname" name="surname" required>
          <p>{{Error}}</p>
          <div class="button" @click="click_button1">Next</div>
         </div>
    </form>
        </v-stepper-content>

            <v-stepper-content step="2">
     <form>
        <div class="container">
        <h1>Password</h1>
        <p>Please fill in this form to create an account.</p>
        <hr>

    <label for="psw"><b>Password</b></label>
    <input v-model="password" type="password" placeholder="Enter Password" name="psw" required>
    <label for="psw-repeat"><b>Repeat Password</b></label>
    <input v-model="password2" type="password" placeholder="Repeat Password" name="psw-repeat" required>
    <hr>
    <p>{{Error}}</p>
    <div class="button" @click="click_button2">Next</div>

  </div>
</form>        
 </v-stepper-content>
            <v-stepper-content step="3">
               <form>
        <div class="container">
        <h1>Добро пожаловать!</h1>
        <h3>Ваш аккаунт создан</h3>
        <hr>
                         <p>Ваш email:{{email}} </p>
                         <p>Ваше имя: {{name}}</p>
                         <p>Ваша фамилия: {{surname}}</p>
                        <div class="button" @click="click_reset">Resert</div>
  </div>
</form>
            </v-stepper-content>
        </v-stepper-items>
        </v-stepper>
  </div>
   
</template>


<script >

export default {
    name: 'Stepper1',

    data: function(){
    return { 
      //  currentTab:0,
        name:"",
        surname:"",
        email:"",
        password:"",
        password2:"",
        Error:"",
        numStep: 1
    }
      
    },
    methods:{
click_button1: function() {

    if(this.name==""||this.surname==""||this.email=="")
      this.Error = "Enter your data"

    else
     {
        this.numStep = this.numStep+1
        this.Error=""
     }

  /*  if(this.password==""||this.password2=="")
      this.Error = "Enter password or reapet password"
    else
      this.numStep = this.numStep+1
  */
},
click_button2: function() {

   if((this.password==""||this.password2=="")||(this.password!=this.password2))
      this.Error = "Enter password or your passwords not qual"    
  else
    {
      this.numStep = this.numStep+1
      this.Error=""
    }
    
},
click_reset : function() {
    this.numStep=1
    this.email=""
    this.name=""
    this.surname=""
    this.password=""
    this.password2=""
}, 


}
}
</script>
<style scoped>
* {box-sizing: border-box}

/* Add padding to containers */
.container {
  padding: 16px;
  background-color: rgb(216, 241, 210);
}

/* Full-width input fields */
input[type=text], input[type=password] {
  width: 100%;
  padding: 15px;
  margin: 5px 0 22px 0;
  display: inline-block;
  border: none;
  background: #a1ce87;
}

input[type=text]:focus, input[type=password]:focus {
  background-color: #ddd;
  outline: none;
}

/* Overwrite default styles of hr */
hr {
  border: 1px dotted #362a2a;
  margin-bottom: 25px;
}

/* Set a style for the submit/register button */
.button {
  background-color: #4CAF50;
  color: white;
  padding: 16px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 100%;
  opacity: 0.9;
}

.registerbtn:hover {
  opacity:1;
}

/* Add a blue text color to links */
a {
  color: dodgerblue;
}

/* Set a grey background color and center the text of the "sign in" section */
.signin {
  background-color: #f1f1f1;
  text-align: center;
}
</style>