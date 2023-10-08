<script setup>
   const id = ref('')
   const password = ref('');

   const emit = defineEmits(['on-login'])

   function onLogin() {
      emit('on-login', {id: id.value, password: password.value})
   }

</script>

<template>
   <form class="login-input" @submit.prevent="onLogin">
      <input type="text" placeholder="Username" v-model="id" />
      <input type="password" placeholder="Password" v-model="password" />
      <button type="submit">Login</button>
   </form>
</template>