<template>
    <nav class="navbar" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item" href="/">Home</a>
        <button class="button navbar-burger">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
      <div class="navbar-menu">
        <div class="navbar-end">
          <nuxt-link class="navbar-item" to="/leagues">Leagues</nuxt-link>
          <nuxt-link class="navbar-item" to="/nba">NBA</nuxt-link>
          <nuxt-link class="navbar-item" to="/secure">Secure</nuxt-link>
          <nuxt-link class="navbar-item" to="/login" v-if="!isAuth">Login</nuxt-link>
          <a class="navbar-item" to="/" @click="doLogout" v-if="isAuth">Logout</a>
        </div>
      </div>
    </nav>
</template>

<script>
import axios from 'axios'
import { mapActions, mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters(['isAuth'])
  },
  methods: {
    async doLogout () {
      await axios.post('/api/logout')
      this.logout()
      this.$router.push('/')
    },
    ...mapActions(['logout'])
  }
}
</script>  

<style lang="scss">
  
</style>