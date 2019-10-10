<template>
  <div class="navbar navbar-expand-lg navbar-light navbar-header p-3">
    <a class="navbar-brand brand" href="/">
      <b>[ I N S I D E ]</b>
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarNavAltMarkup"
      aria-controls="navbarNavAltMarkup"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <!-- collapse -->
    <div class="navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav ml-auto">
        <a class="nav-item nav-link ml-5" href="#">
          <i class="fas fa-search navbar-icon"></i>
        </a>
        <router-link class="nav-item nav-link ml-5" to="/auth/login">
          <i class="far fa-user navbar-icon"></i>
        </router-link>
        <a class="btn-sponsorship ml-5">SPONSORSHIP</a>
      </div>
    </div>
  </div>
</template>
<script>
export default {}
</script>
<style scoped>
.navbar-header {
  background: #fff !important;
}

.brand {
  font-size: 2em;
  font-weight: 800;
  color: #ff5c03;
}

.navbar-icon {
  font-size: 1.8em;
  color: #ff5c03;
}

.btn-sponsorship {
  color: #ff5c03 !important;
  padding: 0.6em;
  border: 1px solid;
  border-color: #ff5c03;
  border-radius: 0.25rem;
}

.btn-sponsorship:hover {
  color: #fff !important;
  background: #ff5c03;
  transition: 0.5s;
}
</style>
