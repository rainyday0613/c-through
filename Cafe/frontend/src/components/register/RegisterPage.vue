<template>
  <form @submit.prevent="submit">
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
              <input id="username" type="text" class="validate" v-model="name">
              <label for="username" class="center-align">Username</label>
            </div>
          </div>
          <div class="row margin">
            <div class="input-field col s12">
              <i class="mdi-social-person-outline prefix"></i>
              <input id="username" type="text" class="validate" v-model="nn">
              <label for="username" class="center-align">NickName</label>
            </div>
          </div>
          <div class="row margin">
            <div class="input-field col s12">
              <i class="mdi-communication-email prefix"></i>
              <input id="email" type="email" class="validate" v-model="em">
              <label for="email" class="center-align">Email</label>
            </div>
          </div>
          <div class="row margin">
            <div class="input-field col s12">
              <i class="mdi-action-lock-outline prefix"></i>
              <input id="password" type="password" class="validate" v-model="pw">
              <label for="password">Password</label>
            </div>
          </div>
          <div class="row margin">
            <div class="input-field col s12">
              <i class="mdi-action-lock-outline prefix"></i>
              <input id="password-again" type="password">
              <label for="password-again">Re-type password</label>
            </div>
          </div>
          <div class="row margin">
            <div class="input-field col s12">
              <i class="mdi-social-person-outline prefix"></i>
              <input id="username" type="text" class="validate" v-model="br">
              <label for="username" class="center-align">BirthDay</label>
            </div>
          </div>
          <div class="row">
            <div class="input-field col s12">
              <a href="register.html" class="btn waves-effect waves-light col s12">Register Now</a>
            </div>
            <div class="input-field col s12">
              <p class="margin center medium-small sign-up">Already have an account?
              <a @click="$router.push('/register')">Login</a></p>
            </div>
          </div>
        </form>
      </div>
    </div>
<!--    <div align="center">-->
<!--      <h1 id="getTitle">회원가입</h1>-->
<!--      <table>-->
<!--        <tr>-->
<!--          <td>이름</td>-->
<!--          <td><input type="text" v-model="name" class="block"></td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>아이디</td>-->
<!--          <td><input type="text" v-model="id" class="block"></td>-->
<!--          <td>-->
<!--            <button @click="clickUse(id)" class="block">중복확인</button>-->
<!--          </td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>비밀번호</td>-->
<!--          <td><input type="password" v-model="pw" class="block"></td>-->
<!--        </tr>-->
<!--        <tr>-->
<!--          <td>생일</td>-->
<!--          <td><input type="number" v-model="br" class="block"></td>-->
<!--        </tr>-->
<!--      </table>-->

<!--      <table>-->
<!--        <tr>-->
<!--          <td>-->
<!--            <button @click="registerOK()" class="block">확인</button>-->
<!--          </td>-->
<!--          <td>-->
<!--            <button @click="$router.push('/login')" type="null" class="block">취소</button>-->
<!--          </td>-->
<!--        </tr>-->
<!--      </table>-->
<!--    </div>-->
  </form>
</template>

<script>
import axios from 'axios'

export default {
  name: 'LoginPage',
  data() {
    return {
      name: '',
      id: '',
      pw: '',
      br: '',
      nn: '',
      em: ''
    }
  },
  methods: {
    registerOK() {
      console.log('Register Page submit Name : ' + this.name + ' ID : ' + this.id + ' PW : ' + this.pw + ' BR : ' + this.br)
      const {name, id, pw, br} = this
      this.$emit('registerOK', {name, id, pw, br})
    },
    clickUse(id) {
      console.log('clickUse : ' + id)
      axios.post('http://localhost:1234/register/overlap', {id})
          .then(res => {
            console.log('res : ' + res.status)
            if (res.status === 204) {
              alert('아이디 중복')
            } else {
              alert('사용 가능한 아이디')
            }
          })
          .catch(err => {
            alert(err)
          })
    },
    submit() {
    },
  }
}
</script>

<style>
form {

}
img {
  width: 150px;
  height: 70px;
  opacity: 70%;
}
#login-page{
  width: 600px;
  height: 700px;
}

</style>
