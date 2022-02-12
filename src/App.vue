<template>
 <CreateUser @create-new-user='createNewUser'/>
 <Users :users="users" />
</template>

<script>
import CreateUser from './components/CreateUser'
import Users from './components/Users'

export default {
  name: "App",
  components: {
    CreateUser,
    Users
  },
  data() {
    return {
      tasks: [],
      users: [],
    };
  },
  methods: {
    createNewUser(user){
        this.users = [...this.users, user]
    }
  },
};
</script>
