<template>
  <div class="about">
    <h3>Thank you for your time</h3>
        <button v-on:click="goBack"
        class="btn btn-light">
        Go back
        </button>
  </div>
</template>

<script>
export default {
    methods: {
       goBack(){
            this.$router.replace({ name: "login" });
        }
    }
}
</script>
