<template>
  <div>
    <button @click="emitFetchUsersEvent">Child Button</button>
    <span v-if="loading">fetching users...</span>
    <br></br>
    <span v-if="users">
    <!-- EXERCISE 02: ITERATE OVER ITEMS-->
    <!-- ANSWER -->
    <li>Got the users</li>
    </span>
  </div>
</template>

<script>
export default {
  name: 'Child',
  data() {
    return {
      loading: false,
      users: null,
    };
  },
  methods: {

    emitFetchUsersEvent() {
      this.loading = true;
      this.users = null;
      
      this.$emit
      ('fetchUsers', (res) => {
        this.loading = false;
        this.users = res;
      });
    },
  },
};
</script>

<style>
div {
  display: grid;
  place-items: center;
}
</style>
