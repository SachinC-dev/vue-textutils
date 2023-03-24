<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
  <section>
    <!-- Navigation Bar -->
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">TextUtils</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
          </ul>
          <form class="d-flex" role="search">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-primary" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>

    <!-- Input will be given here -->
    <div class="container">
      <div class="form-floating my-4">
        <textarea class="form-control" placeholder="Enter your text here" id="floatingTextarea2" style="height: 200px"
          v-model="text"></textarea>
      </div>
      <!-- Button for submission -->
      <button v-on:click="uppercase()" class="btn btn-primary me-2">Uppercase</button>
      <button v-on:click="lowercase()" class="btn btn-primary me-2">Lowercase</button>
      <button v-on:click="removeExtraSpaces()" class="btn btn-primary">Remove extra space</button>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      text: '',
    }
  },
  methods: {
    uppercase() {
      this.text = this.text.toUpperCase();
    },
    lowercase() {
      this.text = this.text.toLowerCase();
    },
  },
  removeExtraSpaces() {
    this.text = this.text.replace(/\s+/g, ' ').trim()
  },
}
</script>