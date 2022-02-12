<template>
  <table>
    <tr>
      <th>Firstname</th>
      <th>Lastname</th>
      <th>Married ?</th>
    </tr>
    <tr :key="user.firstname" v-for="user in users">
      <User :user="user" />
    </tr>
  </table>
</template>

<script>
import User from "./User";

export default {
  name: "Users",
  props: {
    users: Array,
  },
  components: {
    User,
  },
};
</script>
