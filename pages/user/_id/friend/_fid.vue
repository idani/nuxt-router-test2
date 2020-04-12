<template>
  <v-card>
    <v-card-title>
      <h1>ユーザ: {{ userId }}の友達: {{ friendId }}の詳細</h1>
    </v-card-title>
    <v-card-actions>
      <v-btn color="primary" :to="`/user/${userId}/friend`">
        <v-icon left>mdi-account-group</v-icon>友達一覧に戻る
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: 'friendDetail',
  validate({ params }) {
    // 数値でなければならない
    return /^\d+$/.test(params.id)
  },
  computed: {
    userId() {
      return this.$route.params.id
    },
    friendId() {
      return this.$route.params.fid
    }
  }
}
</script>

<style scoped></style>
