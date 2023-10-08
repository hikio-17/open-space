<script setup>
   async function handleOnLogin({ id, password }) {
      const token = await api.login({ id, password });

      api.putAccessToken(token);
      console.log(api.getAccessToken())
      navigateTo('/home');
   }
</script>

<template>
   <section class="login-page">
      <header class="login-page__hero">
         <h1>
            <font-awesome-icon :icon="['fas', 'earth']" />
         </h1>
      </header>
      <article class="login-page__main">
         <h2>
            See
            <strong>The World</strong>
            ,
            <br />
            Through Open Space.
         </h2>

         <LoginInput @on-login="handleOnLogin" />
         <p>
            Don&apos;t have an account?
            <NuxtLink to="/register">Register</NuxtLink>
         </p>
      </article>
   </section>
</template>