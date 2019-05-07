<template>
  <section class="container posts-page">
    <div class="columns">
      <div class="column is-3 is-narrow">
        <div class="card">
          <div class="card-content text-center">
            <div>
              <img
                src="https://placehold.it/150x150"
                style="width: 100%; margin-bottom: 16px; border-radius: 2px;"
                alt=""
              >
            </div>
            <h2>ユーザー名</h2>
          </div>
        </div>
        <nuxt-link class="button is-primary" :to="{ path: '/message'}">メッセージ</nuxt-link>
        <nuxt-link class="button is-primary" :to="{ path: '/remind'}">リマインド</nuxt-link>
      </div>
      <div class="column is-9 is-narrow">
        <div class="card">
          <header class="card-header">
            <div class="card-header-title">
              <h3>
                ユーザー名 さんの設定
              </h3>
            </div>
          </header>
          <div class="card-content">
            <table class="table is-fullwidth" >
              <thead>
                <tr>
                  <th prop="key">項目</th>
                  <th prop="value">値</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in userConfigs" :key="item.id">
                  <td>{{ item.key }}</td>
                  <td><input class="input" type="text">{{ item.value }}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    userConfigs() {
      return [
        {
          key: '氏',
          value: ''
        },
        {
          key: '名',
          value: ''
        },
        {
          key: '性別',
          value: ''
        },
        {
          key: '生年月日',
          value: ''
        },
      ]
    }
  }
}
</script>

<style scoped>
.columns {
  width: 100%;
}

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
  width: 100%;
  margin-top: 5px;
}

</style>