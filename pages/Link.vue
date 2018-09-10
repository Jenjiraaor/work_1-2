<template>
  <div>
    <nuxt-link to="/Login"><center>Hello jenjira->click.</center></nuxt-link><br>
    <router-link :to="{ path: '/table'}" replace><center>Register</center></router-link><br>
    <router-link :to="{ path: '/Login'}" push><center>Register</center></router-link><br>
  </div>
</template>
<script>
export default {
  data() {
    return {
      id: 1,
    }
  },
}
</script>