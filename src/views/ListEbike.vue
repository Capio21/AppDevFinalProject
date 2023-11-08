<template>
    <div>
      <nav class="navbar navbar-dark bg-dark fixed-top">
        <!-- ... (your navigation code) ... -->
        <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
  <div class="container">
    <router-link to="/" class="navbar-brand">NWOW E-Bike</router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav ml-auto"> <!-- Use "ml-auto" to align links to the right -->
        <li class="nav-item">
          <router-link to="/" class="nav-link">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/Contact" class="nav-link">Contact</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/Signin" class="nav-link">Sign In</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>


      </nav>
  <br>
  <br>
  <br>
  
      <div class="container mt-5">
        <h2 class="text-center mb-4">E-Bike List</h2>
  
        <!-- Add a button to toggle the form -->
        <button class="btn btn-primary" @click="toggleForm">Add E-Bike</button>
  
        <!-- Display the form when 'showForm' is true -->
        <div v-if="showForm" class="mt-4">
          <h3>{{ isEditing ? 'Edit E-Bike' : 'Add E-Bike' }}</h3>
          <form @submit.prevent="submitForm">
            <div class="mb-3">
              <label for="model" class="form-label">Model</label>
              <input type="text" class="form-control" id="model" v-model="formData.model" required />
            </div>
            <div class="mb-3">
              <label for="price" class="form-label">Price</label>
              <input type="text" class="form-control" id="price" v-model="formData.price" required />
            </div>
            <div class="mb-3">
              <label for="range" class="form-label">Range</label>
              <input type="text" class="form-control" id="range" v-model="formData.range" required />
            </div>
            <div class="mb-3">
              <label for="motorPower" class="form-label">Motor Power</label>
              <input type="text" class="form-control" id="motorPower" v-model="formData.motorPower" required />
            </div>
            <div class="mb-3">
              <label for="imageSrc" class="form-label">Image URL</label>
              <input type="text" class="form-control" id="imageSrc" v-model="formData.imageSrc" />
            </div>
            <button type="submit" class="btn btn-primary">{{ isEditing ? 'Save' : 'Add' }}</button>
          </form>
        </div>
  
        <div class="table-responsive mt-4">
          <table class="table table-striped table-bordered">
            <thead class="thead-dark">
              <tr>
                <th>Model</th>
                <th>Price</th>
                <th>Range</th>
                <th>Motor Power</th>
                <th>Image</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(ebike, index) in ebikes" :key="index">
                <td>{{ ebike.model }}</td>
                <td>{{ ebike.price }}</td>
                <td>{{ ebike.range }}</td>
                <td>{{ ebike.motorPower }}</td>
                <td>
                  <img :src="ebike.imageSrc" alt="E-Bike Image" style="max-width: 100px; max-height: 100px;" />
                </td>
                <td>
  <button class="btn btn-secondary" @click="editEbike(index)">Edit</button>
  &nbsp; <!-- Add space between buttons -->
  <button class="btn btn-danger" @click="deleteEbike(index)">Delete</button>
</td>

              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        ebikes: [
          { model: 'E-Bike Model 1', price: '$1000', range: '50 miles', motorPower: '250W', imageSrc: 'path/to/your/image1.jpg' },
          { model: 'E-Bike Model 2', price: '$1200', range: '60 miles', motorPower: '350W', imageSrc: 'path/to/your/image2.jpg' },
          { model: 'E-Bike Model 3', price: '$900', range: '40 miles', motorPower: '200W', imageSrc: 'path/to/your/image3.jpg' },
          // Add more E-Bike data here
        ],
        showForm: false,
        isEditing: false,
        formData: {
          model: '',
          price: '',
          range: '',
          motorPower: '',
          imageSrc: '',
        },
        editIndex: -1,
      };
    },
    methods: {
      toggleForm() {
        this.showForm = !this.showForm;
        this.isEditing = false;
        this.formData = {
          model: '',
          price: '',
          range: '',
          motorPower: '',
          imageSrc: '',
        };
      },
      submitForm() {
        if (this.isEditing) {
          this.ebikes[this.editIndex] = { ...this.formData };
        } else {
          this.ebikes.push({ ...this.formData });
        }
        this.toggleForm();
      },
      editEbike(index) {
        this.showForm = true;
        this.isEditing = true;
        this.formData = { ...this.ebikes[index] };
        this.editIndex = index;
      },
      deleteEbike(index) {
        this.ebikes.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add your component-specific styles here */
  
  .table {
    width: 100%;
    border-collapse: collapse;
  }
  
  .table thead th {
    text-align: center;
  }
  
  .table tbody td {
    text-align: center;
  }
  
  .table thead th,
  .table tbody td {
    padding: 10px;
  }
  
  .table thead th {
    background-color: #343a40;
    color: #fff;
  }
  
  .table tbody tr:nth-child(even) {
    background-color: #f2f2f2;
  }
  
  
  </style>
  