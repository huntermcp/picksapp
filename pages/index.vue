<template>
  <section class="container">
    <div>
      <h1 class="title">
        picksapp
      </h1>
         <h2 class="subtitle">
        front end for sports lineups, picks and lines </h2>
      <app-logo/>
    <div header="auth test">
      <div v-if="isAuth">I'm authenticated</div>
    </div>
   
     
    </div>
  </section>
</template>

<script>
import { mapGetters } from 'vuex'
import AppLogo from '~/components/AppLogo.vue'


export default {
  components: {
    AppLogo
    
  },
  computed: {
    ...mapGetters(['isAuth'])
  }
  
}

</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

