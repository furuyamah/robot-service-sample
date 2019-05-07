<template>
  <section class="container posts-page">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          ロボット一覧
        </p>
      </header>
      <div class="card-content">
        <table class="table is-fullwidth" >
          <thead>
            <tr>
              <th prop="id">個体番号</th>
              <th prop="name">名前</th>
              <th prop="user_name">所持ユーザー</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="robot in showRobots" :key="robot.id">
              <td>{{ robot.id }}</td>
              <td>{{ robot.name }}</td>
              <td>{{ robot.user_name }}</td>
            </tr>
          </tbody>
        </table>
        <nuxt-link :to="{ path: 'admin' }">管理者トップページへ戻る</nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    showRobots() {
      return [
        {
          id: '001',
          name: 'Natalia',
          user_name: '高森 藍子',
        },
        {
          id: '002',
          name: 'Micha',
          user_name: '椎名 香織',
        },
        {
          id: '003',
          name: 'Mari',
          user_name: '敦盛 雄二',
        },
        {
          id: '004',
          name: 'Pascal',
          user_name: '宮森 紅羽',
        },
        {
          id: '005',
          name: 'Maxi',
          user_name: '高木 健',
        },
      ]
    }
  }
}
</script>

<style scoped>
.card {
  margin-top: 10px;
  width: 100%;
}
</style>