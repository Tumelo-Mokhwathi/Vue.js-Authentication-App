<template>
  <div id="app">
      <div id="nav" class="myClass">
           <router-link to="/"
                        v-if="authenticated"
                        v-on:click.native="logout"><i class="fas fa-sign-out-alt fa-1x"><font face="verdana"> Sign out </font></i></router-link> 
      </div>
      <router-view @authenticated="setAuthentication"/>
  </div>
</template>

<script>
export default {
  data(){
     return {
       authenticated: false,
       mockAccount:{
          username: ["tumelo"],
          password: ["doctor20"]
       }
     }
  },
  name: "app",
  methods: {
      setAuthentication(status){
         this.authenticated = status;
      },
      logout(){
         this.authenticated = false;
      }
   },
  mounted(){
     if(this.authenticated){
       this.$router.replace({ name: "login"});
     }
   }
};
</script>

<style>
.myClass{
    position: fixed;
    top: 0;
    right: 5px;
    z-index: 1030;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
