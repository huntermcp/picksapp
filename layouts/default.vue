<template>
<div>
    <div>
      <NavBar />
    </div>
    <nuxt/>
</div>
</template>

<script>
import axios from 'axios'
import { mapActions, mapGetters } from 'vuex'
import NavBar from '~/components/navbar.vue'
export default {
  components: {
    NavBar
  },
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