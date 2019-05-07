<template>
  <section class="container">
    <nuxt-link class="button is-primary" :to="{ path: '/users'}">ユーザー一覧</nuxt-link>
    <nuxt-link class="button is-primary" :to="{ path: '/robots'}">ロボット一覧</nuxt-link>
  </section>
</template>


<style scoped>
.container {
  text-align: center;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.button {
  flex: 1;
  width: 50%;
  margin: 10%;
}

</style>