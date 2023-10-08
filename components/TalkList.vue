<script setup>
   const props = defineProps(['talks'])
</script>

<template>
   <div class="talks-list">
      <TalkItem v-for="talk in props.talks" :talk="talk" key="talk.id" />
   </div>
</template>