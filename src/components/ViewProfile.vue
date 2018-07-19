<template>
  <div class="view-profile">
    <h2>View Profile for {{ userID }}</h2>
    </div>
</template>

<script>
export default {
  name: 'ViewProfile',
  data() {
    return {
      userID: this.$route.params.user_id
    }
  },
  methods: {
    updateId() {
      this.userID = this.$route.params.user_id
    }
  },
  watch: {
    $route: 'updateId'
  }
}
</script>

<style>

</style>

