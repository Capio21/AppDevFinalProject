<template>
      <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
      <router-link to="/" class="navbar-brand">NWOW E-Bike</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ml-auto">
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
  

    <div id="app">
        <div class="container mt-5">
            <div class="card p-4">
                <br>
                <br>
                <h1 class="text-center">Assignment Management</h1>

                <form @submit.prevent="assignTask">
                    <div class="mb-3">
                        <label for="mechanicName" class="form-label">Mechanic Name:</label>
                        <input v-model="mechanicName" type="text" class="form-control" id="mechanicName" required />
                    </div>

                    <div class="mb-3">
                        <label for="assignmentDetails" class="form-label">Assignment Details:</label>
                        <textarea v-model="assignmentDetails" class="form-control" id="assignmentDetails" rows="4" required></textarea>
                    </div>

                    <button type="submit" class="btn btn-primary">Assign</button>
                </form>

                <h2 class="mt-4">Assigned Tasks</h2>

                <!-- Replace the <ul> with a <table> -->
                <table class="table">
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Assignment</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(task, index) in assignedTasks" :key="index">
                            <td>{{ task.mechanicName }}</td>
                            <td>{{ task.assignmentDetails }}</td>
                        </tr>
                    </tbody>
                </table>
                <!-- End of the table -->
            </div>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        mechanicName: "",
        assignmentDetails: "",
        assignedTasks: [],
      };
    },
    methods: {
      assignTask() {
        if (this.mechanicName && this.assignmentDetails) {
          this.assignedTasks.push({
            mechanicName: this.mechanicName,
            assignmentDetails: this.assignmentDetails,
          });
  
          // Clear the form inputs
          this.mechanicName = "";
          this.assignmentDetails = "";
        }
      },
    },
  };
  </script>
  
  
  