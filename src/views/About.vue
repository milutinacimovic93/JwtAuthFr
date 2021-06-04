<template>
  <div class="about">
    <b-button @click="logout" variant= "dark">Logout</b-button>
  </div>
</template>
<script>
  import { authService } from '../services/auth.service'
  export default {
    methods: {
      logout() {
        authService.logout().then(() => {
          this.$router.push('/login')
        })
      }
    },

    created() {
      authService.getUsers().then(response => {
        console.log(response);
      })
    }
  }
</script>