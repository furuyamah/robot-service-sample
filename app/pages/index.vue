<template>
  <section class="container">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          <a class="navbar-item" :route="{path: '/'}" >
            ログイン
          </a>
        </p>
      </header>
      <div class="card-content">
        <div class="content">
          <form>
            <div class="field">
              <label class="label">ユーザーID</label>
              <div class="control">
                <input class="input" type="text" placeholder="" v-model="formData.id">
                <label class="checkbox">
                <input type="checkbox" v-model="isAdmin">
                  管理者ログインする
                </label>
                <nuxt-link class="button is-primary" :to="{ path: 'admin' }" v-if="isAdmin">{{ buttonText}}</nuxt-link>
                <nuxt-link class="button is-primary" :to="{ path: `/users/${formData.id}`}" v-else>{{ buttonText}}</nuxt-link>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  asyncData() {
    return {
      isAdmin: false,
      formData: {
        id: ''
      }
    }
  },
  computed: {
    buttonText() {
      return this.isAdmin ? '管理者ログイン' : 'ユーザーログイン'
    }
  }
}
</script>


<style scoped>
.card {
  margin-top: 10px;
}

.control {
  margin-bottom: 10px;
}

.is-primary {
  float: right;
  margin-top: 10px;
}
</style>
