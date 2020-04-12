<template>
  <v-card>
    <v-card-title>
      <h1>ユーザID: {{ userId }}の友達一覧</h1>
    </v-card-title>
    <v-card-actions>
      <v-btn small color="primary" :to="`/user/${userId}`">戻る</v-btn>
    </v-card-actions>

    <v-card-text>
      <v-simple-table>
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left" width="50">fid</th>
              <th class="text-left">Name</th>
              <th width="200"></th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="user in users" :key="user.id">
              <td class="text-right">{{ user.id }}</td>
              <td>{{ user.name }}</td>
              <td>
                <v-btn color="primary" small :to="`${user.id}`" append>
                  <v-icon left>mdi-account-details</v-icon>
                  友達詳細
                </v-btn>
              </td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'index',
  validate({ params }) {
    // 数値でなければならない
    return /^\d+$/.test(params.id)
  },
  data() {
    return {
      users: [
        {
          name: 'Frozen Yogurt',
          id: 159
        },
        {
          name: 'Ice cream sandwich',
          id: 237
        },
        {
          name: 'Eclair',
          id: 262
        },
        {
          name: 'Cupcake',
          id: 305
        },
        {
          name: 'Gingerbread',
          id: 356
        },
        {
          name: 'Jelly bean',
          id: 375
        },
        {
          name: 'Lollipop',
          id: 392
        },
        {
          name: 'Honeycomb',
          id: 408
        },
        {
          name: 'Donut',
          id: 452
        },
        {
          name: 'KitKat',
          id: 518
        }
      ]
    }
  },
  computed: {
    userId() {
      return this.$route.params.id
    }
  }
}
</script>

<style scoped></style>
