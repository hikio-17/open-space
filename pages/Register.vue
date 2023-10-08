<script setup>
   import api from '~/utils/api'

   async function handleOnRegister({ id, name, password }) {
      await api.register({ id, name, password });
      navigateTo('/');
   }
</script>

<template>
   <section class="register-page">
      <header class="register-page__hero">
         <h1>
            <font-awesome-icon :icon="['fas', 'earth']" />
         </h1>
      </header>
      <article class="register-page__main">
         <h2>Create your account</h2>
         <RegisterInput @on-register="handleOnRegister" />

         <p>
            Already have an account?
            <NuxtLink to="/">Login</NuxtLink>
         </p>
      </article>
   </section>
</template>