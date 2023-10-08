<script setup>
import { onMounted } from 'vue'

const talks = ref([])
const users = ref([])
const authUser = ref({})
const talksList = ref([])

const getTalks = async () => {
   const data = await api.getAllTalks();
   talks.value = data;
}

const getUsers = async () => {
   const data = await api.getAllUsers()
   users.value = data
}

const getAuthUser = async () => {
   const data = await api.getOwnProfile();
   authUser.value = data;
}

onMounted( async () => {
   await getTalks()
   await getUsers()
   await getAuthUser()

   talksList.value = talks.value.map((talk) => ({
      ...talk,
      user: users.value.find((user) => user.id === talk.user),
      authUser: authUser.value.id
   }))
})

console.log(talksList.value[0])


</script>

<template>
   <section class="home-page">
      <TalkInput />
      <TalkList :talks="talksList" />
   </section>
</template>