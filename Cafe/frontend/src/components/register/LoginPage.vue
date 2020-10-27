<template>
  <div id="login-page" class="row">
    <div class="col s12 z-depth-6 card-panel">
      <form class="login-form">
        <div class="row">
          <div class="input-field col s12 center">
            <img src="https://previews.123rf.com/images/pimonova/pimonova1412/pimonova141200047/34661078-%EC%86%90-%EC%8A%A4%EC%BC%80%EC%B9%98-%EB%B9%88%ED%8B%B0%EC%A7%80-%EC%BB%A4%ED%94%BC-%EC%84%B8%ED%8A%B8%EB%A5%BC-%EA%B7%B8%EB%A0%A4-%EB%B2%A1%ED%84%B0-%EC%9D%BC%EB%9F%AC%EC%8A%A4%ED%8A%B8-%EB%A0%88%EC%9D%B4-%EC%85%98-%EC%B9%B4%ED%8E%98%EC%99%80-%EB%A0%88%EC%8A%A4%ED%86%A0%EB%9E%91-%EB%A9%94%EB%89%B4-%EB%94%94%EC%9E%90%EC%9D%B8.jpg" alt="" class="responsive-img valign profile-image-login">
          </div>
        </div>
        <div class="row margin">
          <div class="input-field col s12">
            <i class="mdi-social-person-outline prefix"></i>
            <input class="validate" v-model="id" id="email" type="email">
            <label for="email" data-error="wrong" data-success="right" class="center-align">Email</label>
          </div>
        </div>
        <div class="row margin">
          <div class="input-field col s12">
            <i class="mdi-action-lock-outline prefix"></i>
            <input id="password" type="password" v-model="pw">
            <label for="password">Password</label>
          </div>
        </div>
        <div class="row">
          <div class="input-field col s12">
            <a href="login.html" class="btn waves-effect waves-light col s12">Login</a>
          </div>
        </div>
        <div class="row">
          <div class="input-field col s6 m6 l6">
            <p class="medium-small"><a @click="$router.push('/register')">Sign Up Now!</a></p>
          </div>
          <div class="input-field col s6 m6 l6">
            <p class="medium-small"><a @click="$router.push('/login/findid')">Forgot ID?</a></p>
          </div>
          <div class="input-field col s6 m6 l6">
            <p class="medium-small"><a @click="$router.push('/login/findpw')">Forgot PW?</a></p>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
    return {
      id: '',
      pw: ''
    }
  },
  methods: {
    login() {
      console.log('Login Page submit ID : ' + this.id + 'PW : ' + this.pw)
      const {id, pw} = this
      this.$emit('login', {id, pw})
    },
    submit() {
    }
  }
}
</script>
<style>
#login-page {
  width: 600px;
  height: 700px;
  margin-top: 30px;
}
img {
  width: 150px;
  height: 70px;
  opacity: 70%;
}
.col s12 z-depth-6 card-panel {
  border: 0px none;
}
a:hover {
  background-color: lightgray;
  transition: background-color 1s;
}
.medium-small {
  display: flex;
  justify-content: center;
}

.row {
  display: flex;
  justify-content: space-around;
}
</style>