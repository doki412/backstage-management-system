<template>
  <div class="customers container">
    <Alert v-if="alert" :message="alert"></Alert>
    <table class="table table-striped">
      <thead>
        <tr>
          <th>姓名</th>
          <th>电话</th>
          <th>邮箱</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="customer in customers">
          <td>{{customer.name}}</td>
          <td>{{customer.tel}}</td>
          <td>{{customer.email}}</td>
          <td><router-link class="btn btn-default" :to="'/customer/'+customer.id">详情</router-link></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  import Alert from "./Alert"
  export default {
    name: 'customers',
    data() {
      return {
        customers: [],
        alert: ""
      }
    },
    methods: {
      fetchCustomers() {
        this.$http.get("http://localhost:3000/users")
          .then(function (response) { this.customers = response.body })
      }
    },
    created() {
      if(this.$route.query.alert){
        this.alert = this.$route.query.alert
      }
      this.fetchCustomers()
    },
    updated() {
      this.fetchCustomers()
    },
    components: {
      Alert
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>