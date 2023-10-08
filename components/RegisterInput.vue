<script setup>
   const id = ref('')
   const name = ref('')
   const password = ref('')

   const emit = defineEmits(['on-register'])

   function onRegister() {
      emit('on-register', { id: id.value, name: name.value, password: password.value});
   }

</script>

<template>
   <form @submit.prevent="onRegister" class="register-input">
      <input type="text" placeholder="Name" v-model="id" />
      <input type="text" placeholder="Username" v-model="name" />
      <input type="password" placeholder="Password" v-model="password" />
      <button type="submit">Register</button>
    </form>
</template>