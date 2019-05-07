<template>
  <section class="container posts-page">
    <div class="control">
      <label class="label">送りたいメッセージ</label>
      <input class="input" type="text" placeholder="Text input">
      <div class="button-wrapper">
        <button class="button is-primary">Send</button>
        <button class="button is-primary">Send with timer</button>
      </div>
    </div>
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          メッセージログ
        </p>
      </header>
      <div class="card-content">
        <table class="table is-fullwidth" >
          <thead>
            <tr>
              <th prop="id">ID</th>
              <th prop="name">本文</th>
              <th prop="send_at">送信日時</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="log in showLogs" :key="log.id">
              <td>{{ log.id }}</td>
              <td>{{ log.body }}</td>
              <td>{{ log.send_at }}</td>
            </tr>
          </tbody>
        </table>
        <nuxt-link :to="{ path: 'user' }">トップページへ戻る</nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    showLogs() {
      return [
        {
          id: '001',
          body: 'Natalia',
          send_at: '2019/05/07 18:23:46'
        },
        {
          id: '002',
          body: 'Micha',
          send_at: '2019/05/07 19:23:46'
        },
        {
          id: '003',
          body: 'Mari',
          send_at: '2019/05/07 20:23:46'
        },
        {
          id: '004',
          body: 'Pascal',
          send_at: '2019/05/07 21:23:46'
        },
        {
          id: '005',
          body: 'Maxi',
          send_at: '2019/05/07 22:23:46'
        },
      ]
    }
  }
}
</script>

<style scoped>
.card {
  margin-top: 100px;
  width: 100%;
}

.button-wrapper {
  display: flex;
  margin-bottom: 5%;
}

.button {
  flex: 1;
  margin: 0px 20px;
}
</style>