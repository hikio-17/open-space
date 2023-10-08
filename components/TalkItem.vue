<script setup>
   const props = defineProps(["talk"])
   const { id, text, createdAt, likes, user, authUser, like } = props.talk
</script>

<template>
   <div role="button" tabIndex={0} class="talk-item">
      <div class="talk-item__user-photo">
         <img :src="user.photo" :alt="user" />
      </div>

      <div class="talk-item__detail">
         <header>
            <div class="talk-item__user-info">
               <p class="talk-item__user-name">{{ user.name }}</p>
               <p class="talk-item__user-id">
                  @
                  {{ user.id }}
               </p>
            </div>
            <p class="talk-item__created-at">{{ postedAt(createdAt) }}</p>
         </header>
         <article>
            <p class="talk-item__text">{{ text }}</p>
         </article>

         <div class="talk-item__likes">
            <p>
               <button type="button" aria-label="like">
                  Icon
               </button>
               likes length
            </p>
         </div>
      </div>
   </div>
</template>