<template>
  <div class="all">
    <div v-if="isLoggedin" class="loggedin-cont">
      <div class="nav">
        <h1 class="app-name">Zeraf Dev Chat</h1>
        <Avatar :src="user.photoURL" />
         <button class="logout-btn" @click="signOut">
          Log out
        </button>
        </div>
        <div class="chat">
          <ChatView />
        </div>
      </div> 
     
      <div v-else class="page-container">
         <div class="login-page">
           <h1 class="app-name-login"><strong class="strong">Zeraf Tech</strong>  Dev Chat</h1>
            <h4>Chat with Developers @Zeraf Technologies </h4>
            <p>Let's us know how we can help you</p>
            <button class="login-btn" @click="signIn">
                Log In With Google
            </button>
         </div>
      
      </div> 
  </div>
</template>

<script>
import Avatar from './Avatar.vue'
import ChatView from './ChatView.vue'
import { authMtd } from '@/firebase'

export default {
  components: { Avatar, ChatView },
  setup() {
    const { user, isLoggedin, signOut, signIn } = authMtd()
    return { user, isLoggedin, signOut, signIn }
  }
}
</script>
<style scoped>
.page-container{
  background-image: url('~@/assets/bg.svg');
  background-position: center center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  background-color: blueviolet;
}
.chat{
  justify-content: center;
  align-content: center;
  display: block;
  margin-left: 20%;
  margin-right: 20%;
  margin-top: 0.5%;
  margin-bottom: 0;
  padding: 0;
}
.app-name-login{
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  padding-right: 25rem;
  color: white;
  font-size: 3rem;
  margin-left: 10%;
  text-align: left;
  font-weight: bolder;
}

h4{
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  color: white;
  text-align: left;
  margin-top: 3%;
  margin-left: 10%;
}
p{
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  color: white;
  text-align: left;
  margin-left: 10%;
  margin-top: 3%;
}
.app-name{
  padding-left: 7%;
  padding-right: 40%;
  color: white;
  align-items: center;
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
}
.all{
  background-color: white;
  min-height: 100vh;
}
.login-page{
  padding-left: 14rem;
  padding-top: 11rem;
  height: auto;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-attachment: fixed;
} 
.login-btn{
  appearance: none;
  border: none;
  outline: none;
  background: none;
  display: block;
  margin: 1.5rem;
  background-color: white;
  color: lightslategrey;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  border: solid 0.15rem white;
  padding: 1rem;
  font-weight: bold;
  border-radius: 999px;
  margin-left: 10%;
  margin-top: 3%;
  box-shadow: 0px 0.7px 2.8px black;
}
.login-btn:hover{
  margin: 1.5rem;
  background-color: lightslategrey;
  color: white;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  border: solid 0.15rem lightslategray;
  padding: 1rem;
  border-radius: 999px;
  margin-left: 10%;
  margin-top: 3%;
  box-shadow: 0.4px 0.4px 3.8px black;
}
.logout-btn{
  appearance: none;
  border: none;
  outline: none;
  background: none;
  display: block;
  box-shadow: 0px 0px 3px white;
  margin: 0.5%;
  margin-left: 3%;
  background-color: lightslategray;
  color: white;
  text-justify: center;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  border: solid 0.15rem white;
  padding: 0.6rem;
  border-radius: 999px;
  float: right;
}
.nav{
  box-shadow: 0px 0px 12px lightslategrey;
  background-attachment: fixed;
  background-color: lightslategray;
  width: 100%;
  display: flex;
  align-items: center;
  max-height: 8rem;
  z-index: 20px;
  position: sticky;
}

</style>