<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <input
        type="text"
        v-model="firstname"
        name="firstname"
        placeholder="Firstname"
      />
    </div>
    <div class="form-control">
      <input
        type="text"
        v-model="lastname"
        name="lastname"
        placeholder="Lastname"
      />
    </div>
    <div class="form-control form-control-check">
      Married? <input type="checkbox" v-model="married" name="married" />
    </div>
    <input type="submit" value="Submit" />
  </form>
</template>

<script>
export default {
  name: "CreateUser",
  data() {
    return { firstname: "", lastname: "", married: false };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      const newUser = {
        firstname: this.firstname,
        lastname: this.lastname,
        married: this.married,
      };
      this.$emit("create-new-user", newUser);

      this.firstname = '',
      this.lastname = '',
      this.married = false
    },
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
  width: 200px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>
