<template>
  <v-card>
    <v-card-title>
      <h1>ユーザ: {{ userId }}</h1>
    </v-card-title>
    <v-card-text>
      <nuxt-child />
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'friend',
  computed: {
    userId() {
      return this.$route.params.id
    }
  }
}
</script>

<style scoped></style>
