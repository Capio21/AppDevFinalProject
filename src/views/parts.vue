<template>
  <div>
    <div class="container mt-4">
      <h1 class="text-center">E-Bike Parts</h1>

      <div class="row">
        <!-- Center the column using mx-auto class -->
        <div class="col-md-4 mx-auto" v-for="part in eBikeParts" :key="part.partNumber">
          <div class="card mb-3">
            <div class="card-body">
              <h5 class="card-title">{{ part.partName }}</h5>
              <p class="card-text">Part Number: {{ part.partNumber }}</p>
              <p class="card-text">{{ part.description }}</p>
              <p class="card-text">Price: {{ part.price }}</p>
              <p class="card-text">In Stock: {{ part.inStock ? 'Yes' : 'No' }}</p>
              <button @click="deletePart(part.partNumber)" class="btn btn-danger">Delete</button>
            </div>
          </div>
        </div>
      </div>

      <div class="row">
        <div class="col-md-4 mx-auto">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Add New Part</h5>
              <div class="form-group">
                <label for="newPartName">Part Name</label>
                <input v-model="newPartName" type="text" class="form-control" id="newPartName">
              </div>
              <div class="form-group">
                <label for="newPartNumber">Part Number</label>
                <input v-model="newPartNumber" type="text" class="form-control" id="newPartNumber">
              </div>
              <div class="form-group">
                <label for="newDescription">Description</label>
                <textarea v-model="newDescription" class="form-control" id="newDescription" rows="2"></textarea>
              </div>
              <div class="form-group">
                <label for="newPrice">Price</label>
                <input v-model="newPrice" type="text" class="form-control" id="newPrice">
              </div>
              <div class="form-check">
                <input v-model="newInStock" type="checkbox" class="form-check-input" id="newInStock">
                <label class="form-check-label" :for="newInStock">In Stock</label>
              </div>
              <button @click="addPart" class="btn btn-success mt-3">Add Part</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

  
  
  <script>
  export default {
    data() {
      return {
        eBikeParts: [
          {
            partName: 'Battery',
            partNumber: 'EBP1234',
            description: 'High-capacity lithium-ion battery',
            price: '$299.99',
            inStock: true,
          },
          {
            partName: 'Motor',
            partNumber: 'EM123',
            description: '250W brushless electric motor',
            price: '$199.99',
            inStock: true,
          },
          {
            partName: 'Controller',
            partNumber: 'EC456',
            description: 'Advanced control unit',
            price: '$89.99',
            inStock: true,
          },
          // Add more e-bike parts here
        ],
        newPartName: '',
        newPartNumber: '',
        newDescription: '',
        newPrice: '',
        newInStock: false,
      };
    },
    methods: {
      addPart() {
        this.eBikeParts.push({
          partName: this.newPartName,
          partNumber: this.newPartNumber,
          description: this.newDescription,
          price: this.newPrice,
          inStock: this.newInStock,
        });
        // Clear input fields
        this.newPartName = '';
        this.newPartNumber = '';
        this.newDescription = '';
        this.newPrice = '';
        this.newInStock = false;
      },
      deletePart(partNumber) {
        this.eBikeParts = this.eBikeParts.filter(part => part.partNumber !== partNumber);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add any scoped styles here */
  </style>
  