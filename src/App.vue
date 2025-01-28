<template>
  <input type="text" v-model="userName" placeholder="Имя">
  <input type="password" v-model="userPass" placeholder="Пароль">
  <input type="email" v-model="userEmail" placeholder="Email">
  <p className="error">{{ error }}</p>
  <button @click="sendData()">Отправить</button>

<div v-if="users.length==0" className="user">
  <p>У нас нет пользователей</p>
</div>
<div v-else-if="users.length==1" className="user">
  <p>У нас только один пользователь</p>
</div>
<div v-else className="user">
  <p>У нас больше одного пользователя</p>
</div>

<div v-for="(el, index) in users" :key="index" className="user">
  <h3>{{ el.name }}</h3>
<p>{{ el.email }} - <b>{{ el.pass }}</b></p>
</div>

  <!-- <p>{{ users }}</p> -->
</template>


<script>
export default {
  data() {
    return {
      users: [],
      error: '',
      userName: '',
      userPass: '',
      userEmail: '',


    }
  },
  methods: {
    sendData() {
      if (this.userName == '') {
        this.error = 'Имя не введено';
        return;
      } else if (this.userPass == '') {
        this.error = 'Пароль не введено';
        return;
      } else if (this.userEmail == '') {
        this.error = 'Email не введено';
        return;
      }
      this.error='';
      this.users.push({
        name: this.userName,
        pass: this.userPass,
        email: this.userEmail,

      })
    }
  }
}
</script>







<style scoped>
.user{
  background-color: grey;
  margin: 1rem;
  color: white;
}
.user p, .user h3{
  padding: 5px;
}
</style>
