<template>
  <base-card>
    <h2>Add Resources</h2>
    <div>
      <form action="" @submit.prevent="submitData">
        <div class="form-control">
          <label for="title">Title</label>
          <input id="title" name="title" type="text" v-model="title"/>
        </div>
        <div class="form-control">
          <label for="description">Description</label>
          <textarea
            v-model="description"
            name="description"
            id="description"
            cols="30"
            rows="10"
          ></textarea>
        </div>
        <div class="form-control">
          <label for="link">Link</label>
          <input id="link" name="link" type="url" v-model="url"/>
        </div>
        <div>
          <base-button type="submit">Add Resource</base-button>
        </div>
      </form>
    </div>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  data(){
    return {
      title: '',
      description: '',
      url: ''
    }
  },
  methods: {
    submitData(){
      this.addResource(this.title, this.description, this.url)
    }
  }
}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
