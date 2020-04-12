<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left" width="50">id</th>
          <th class="text-left">Name</th>
          <th width="200"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td class="text-right">{{ user.id }}</td>
          <td>{{ user.name }}</td>
          <td>
            <v-btn color="primary" small :to="`user/${user.id}`">
              <v-icon left>mdi-account-details</v-icon>
              詳細
            </v-btn>
          </td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
export default {
  name: 'index',
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
  }
}
</script>

<style scoped></style>
