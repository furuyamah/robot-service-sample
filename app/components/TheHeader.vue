<template>
  <nav class="navbar" role="navigation" aria-label="main navigation" :router="true">
    <div class="navbar-brand">
      <nuxt-link class="navbar-item" :to="{ path: '/' }" >
        Nuxt Diary App
     </nuxt-link>
      <nuxt-link class="navbar-item" :to="{ path: '/posts/' }" >
        投稿一覧
     </nuxt-link>
    </div>

    <no-ssr>
      <div class="navbar-end">
        <nuxt-link class="navbar-item" :to="{ path: `/users` }">
          <span>ユーザー</span>
        </nuxt-link>
        <nuxt-link class="navbar-item" :to="{ path: '/' }">
          <span>ログイン</span>
        </nuxt-link>
        <nuxt-link class="navbar-item" :to="{ path: '/posts/new' }">
          <span>新規投稿</span>
        </nuxt-link>
      </div>
    </no-ssr>
  </nav>
</template>

