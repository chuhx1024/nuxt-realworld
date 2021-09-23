<template>
  <div class="signUp-container">
    <div class="auth-page">
      <div class="container page">
        <div class="row">
          <div class="col-md-6 offset-md-3 col-xs-12">
            <h1 class="text-xs-center">
              Sign in
            </h1>

            <ul class="error-messages">
              <!-- <li>That email is already taken</li> -->
            </ul>

            <form>
              <fieldset class="form-group">
                <input v-model="user.email" class="form-control form-control-lg" type="text" placeholder="Email">
              </fieldset>
              <fieldset class="form-group">
                <!-- <input v-model="user.password" class="form-control form-control-lg" type="password" placeholder="Password"> -->
                <input v-model="user.password" class="form-control form-control-lg" placeholder="Password">
              </fieldset>
              <div class="btn btn-lg btn-primary pull-xs-right" @click="fetchSomething">
                Sign up
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SignUp',
  data () {
    return {
      user: {
        email: 'chuhx1024@126.com',
        password: '123456@ope'
      },

      ip: ''
    }
  },
  methods: {
    async fetchSomething () {
      const isOk = await this.$axios.$post('/users/login', { user: this.user })
      if (isOk) {
        this.$router.push('/')
      }
    }
  }

}
</script>

<style scoped>
   .signUp-container {

   }

</style>
