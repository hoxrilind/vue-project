<template>
    <td>{{ user.firstname }}</td>
    <td>{{ user.lastname }}</td>
    <td>{{ user.married }}</td>
</template>

<script>
export default {
  name: "User",
  props: {
    user: Object,
  },
};
</script>
