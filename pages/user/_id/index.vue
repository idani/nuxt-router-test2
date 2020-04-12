<template>
  <v-card>
    <v-card-title>
      <h1>ユーザ: {{ userId }}</h1>
    </v-card-title>
    <v-card-actions>
      <v-btn color="primary" to="friend" append>
        <v-icon left>mdi-account-group</v-icon>友達一覧
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: 'UserDetail',
  validate({ params }) {
    // 数値でなければならない
    return /^\d+$/.test(params.id)
  },
  computed: {
    userId() {
      return this.$route.params.id
    }
  }
}
</script>

<style scoped></style>
