<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div id="app">
    <h1>Checkout Form</h1>
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="">Name</label>
        <input v-model="formData.name" type="text" id="name" required>
      </div>
      <div class="form-group">
        <label for="">Phone Number</label>
        <input v-model="formData.phone" type="number" id="phone" required>
      </div>
      <div class="form-group">
        <label for="">Email</label>
        <input v-model="formData.email" type="email" id="email" required>
      </div>
      <div class="form-group">
        <label for="">Shipping Address</label>
        <textarea v-model="formData.address" type="text" id="address" required></textarea>
      </div>
      <div class="form-group">
        <label for="">Credit Card</label>
        <input v-model="formData.creditCard" type="text" id="creditcard" required>
      </div>
      <button type="submit">Submit order</button>
      <button type="reset" @click="clearForm()">Reset</button>
    </form>
    <div v-if="orderSummitted">
      <!-- <h2>Order Submitted!</h2>
      <p><strong>Name: </strong>{{ formData.name }}</p>
      <p><strong>Email: </strong>{{ formData.email }}</p>
      <p><strong>Shipping Address: </strong>{{ formData.address }}</p>
      <p><strong>Credit Card#: </strong>{{ formData.creditCard }}</p> -->
      <table>
        <tr>
          <th>Name</th>
          <th>Phone Number</th>
          <th>Email</th>
          <th>Address</th>
          <th>Credit Card</th>
        </tr>
        <tr>
          <td>{{formData.name}}</td>
          <td>{{formData.phone}}</td>
          <td>{{formData.email}}</td>
          <td>{{formData.address}}</td>
          <td>{{formData.creditCard}}</td>
          </tr>
      </table>
    </div>

  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      formData: {
        name: '',
        phone: '',
        email: '',
        address: '',
        creditCard: '',
      },
      orderSummitted: false,
    }
  },
  methods: {
    submitForm() {
      this.orderSummitted = true;
    },
    clearForm() {
      this.name = '';
      this.phone = '';
      this.email = '';
      this.address = '';
      this.creditCard = '';
    },

  }
}

</script>

<style>
label {
  display: block;
  margin-bottom: 5px;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  font-size: 15px;
  margin-bottom: 10px;
}

button {
  padding: 15px;
  margin: 5px;
  font-size: 15px;
  background-color: blue;
  color: beige;
  border: none;
  cursor: pointer;
}

table,tr,td,th{
  border: 1px solid black;
  border-collapse: collapse;
  padding: 5px;
}
</style>