<template>
<div class="box">
<form @submit.prevent="submit" novalidate>
  <div class="notification is-danger" v-show="loginFailed">
    <button class="delete"></button>
    Sorry, invalid email or password.
  </div>
  <div class="field">
    <label class="label">Username</label>
    <div class="control">
      <input class="input" v-model="form.username" type="text" placeholder="ASmith">
    </div>
  </div>

  <div class="field">
    <label class="label">Password</label>
    <div class="control">
      <input class="input" type="password" name="password" v-model="form.password" placeholder="password">
    </div>
  </div>
  
  <div class="control">
  <button class="button is-primary" type="submit">Login</button>

</div>
  </form>
  <a> Forgot Password </a><a> Register </a>
</div>
</template>





<script>
import axios from 'axios'
import { mapActions } from 'vuex'
export default {
  data () {
    return {
      form: {
        username: '',
        password: ''
      },
      loginFailed: false
    }
  },
  methods: {
    async submit () {
      await this.$validator.validateAll()
      if (this.errors.any()) {
        return
      }
      try {
        this.loginFailed = false
        await axios.post('/api/login', this.form)
        this.login()
        this.$router.push(`${this.form.username}/profile`)
      } catch (e) {
        console.log('login failed')
        this.loginFailed = true
      }
    },
    ...mapActions(['login'])
  }
}
</script>