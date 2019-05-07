<template>
  <section class="container posts-page">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          ユーザー一覧
        </p>
      </header>
      <div class="card-content">
        <table class="table is-fullwidth" >
          <thead>
            <tr>
              <th prop="name">氏名</th>
              <th prop="sex">性別</th>
              <th prop="birthday">生年月日</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="user in showUsers" :key="user.id">
              <td @click="redirectToUser()">{{ user.name }}</td>
              <td>{{ user.sex }}</td>
              <td>{{ user.birthday }}</td>
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
    showUsers() {
      return [
        {
          id: '001',
          name: '高森 藍子',
          sex: '女',
          birthday: '1994/04/07'
        },
        {
          id: '002',
          name: '椎名 香織',
          sex: '女',
          birthday: '1995/04/07'
        },
        {
          id: '003',
          name: '敦盛 雄二',
          sex: '男',
          birthday: '1996/04/07'
        },
        {
          id: '004',
          name: '宮森 紅羽',
          sex: '女',
          birthday: '1994/08/07'
        },
        {
          id: '005',
          name: '高木 健',
          sex: '男',
          birthday: '1994/02/07'
        },
      ]
    }
  },
  methods: {
    redirectToUser() {
      this.$router.push('/user')
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