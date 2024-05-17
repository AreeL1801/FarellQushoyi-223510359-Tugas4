<template>
  <div id="app">
    <header>
      <h1>Welcome to My Interactive App</h1>
    </header>
    <main>
      <ParentComponent />
      <div class="form-container">
        <h2>Input Form</h2>
        <form @submit.prevent="handleSubmit">
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="name" required />

          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" required />

          <button type="submit">Submit</button>
        </form>
        <div v-if="submitted">
          <h3>Submitted Data</h3>
          <p><strong>Name:</strong> {{ name }}</p>
          <p><strong>Email:</strong> {{ email }}</p>
          <button class="clear-button" @click="clearData">Clear</button>
        </div>
      </div>
    </main>
    <footer>
      <p>&copy; 2024 My App. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  components: {
    ParentComponent
  },
  data() {
    return {
      name: '',
      email: '',
      submitted: false
    };
  },
  methods: {
    handleSubmit() {
      this.submitted = true;
    },
    clearData() {
      this.name = '';
      this.email = '';
      this.submitted = false;
    }
  }
};
</script>

<style scoped>
#app {
  text-align: center;
  font-family: 'Arial', sans-serif;
  color: #333;
  background-color: #add8e6; /* Light blue background */
  min-height: 100vh; /* Full viewport height */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

header {
  background-color: #4CAF50;
  padding: 20px;
  color: white;
}

header h1 {
  margin: 0;
  font-size: 2.5em;
}

main {
  padding: 20px;
  transition: all 0.3s ease-in-out;
}

main:hover {
  transform: scale(1.02);
}

footer {
  background-color: #333;
  color: white;
  padding: 10px;
  width: 100%;
  bottom: 0;
}

.form-container {
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  max-width: 400px;
  background-color: #f9f9f9;
}

.form-container h2 {
  margin-top: 0;
}

.form-container label {
  display: block;
  margin: 10px 0 5px;
}

.form-container input {
  width: calc(100% - 20px);
  padding: 10px;
  margin-bottom: 10px;
}

.form-container button {
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.form-container button:hover {
  background-color: #45a049;
}

.form-container .clear-button {
  margin-top: 10px;
  background-color: #f44336;
}

.form-container .clear-button:hover {
  background-color: #d32f2f;
}
</style>
