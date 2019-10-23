<template>
   <div class="container">
       <div id="myForm" class="card login">
          <div class="card-body">
             <h1>Login Authentication</h1>
             <form class="text-center">
                <div class="form-group">
                <label class="label mr-5 mt-3">Username :</label>
                <input type="text"
                       class="input w-50"
                       placeholder="Username"
                       name="username"
                       v-model="input.username"/>
             </div>
             <div class="form-group">
                <label class="label mr-5 mt-3">Passowrd :</label>
                <input type="text"
                       class="input w-50"
                       placeholder="Password"
                       name="password"
                       v-model="input.password"/>
             </div>
             <div class="form-group">
                 <button type="submit" 
                         id="myLogin" 
                         class="btn btn-primary w-40"
                         v-on:click="login">Login</button>
                 <button type="submit" 
                         id="myExit" 
                         class="btn btn-primary w-40"
                         v-on:click="exit">Exit</button>
             </div>
             </form>
         </div>
       </div>
   </div> 
</template>

<script>
export default {
    data(){
        return {
            input: {
                password: "",
                username: ""
            }
        }
    },
    methods: {
        login(){
            if(this.input.username != "" && this.input.password != ""){
                 if(this.input.username == this.$parent.mockAccount.username && this.input.password == this.$parent.mockAccount.password) {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "secure" });
                } else {
                    console.log("The username or password is incorrect")
                }      
            } else {
                console.log("Enter your username or password")
            }
        },
        exit(){
            console.log("Exit button is clicked")
        }
    }
}
</script>

<style scoped>
  #myForm{
     background-color: #fcf8f3;
  }

  #myLogin{
      margin-left: 120px;
      width: 20%;
  }

  #myExit{
      margin-left: 30px;
      width: 20%;
  }
  .container{
      scroll-margin-top: 180px;
  }

  .login {
    max-width: 500px;
    margin-top: 200px;
    display: block;
    margin-left: auto;
    margin-right: auto;
}
</style>