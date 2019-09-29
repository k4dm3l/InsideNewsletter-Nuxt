<template>
  <div class="footer d-flex">
    <div class="col-12 m-auto pt-5">
      <div class="row">
        <ul class="categorie-list p-2 m-auto">
          <li class="footer-links">RECENT UPDATES</li>
          <li class="footer-links">ABOUT</li>
          <li class="footer-links">PRIVACY POLICY</li>
          <li class="footer-links">SPONSORSHIP</li>
        </ul>
      </div>
      <div class="row">
        <ul class="categorie-list p-2 m-auto">
          <li>Developed by Camilo Acevedo Escalante</li>
        </ul>
      </div>
      <div class="row">
        <ul class="categorie-list p-4 m-auto">
          <li>
            <i class="fab fa-twitter"></i>
          </li>
          <li>
            <i class="fab fa-github"></i>
          </li>
          <li>
            <i class="fab fa-hackerrank"></i>
          </li>
          <li>
            <i class="fas fa-globe"></i>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {}
</script>
<style scoped>
.footer {
  background: #293347;
}

.categorie-list li {
  display: inline;
  margin: 1.3em;
  font-weight: 800;
  color: #fff;
  padding: 1em;
}

.footer-links:hover {
  background: #ff5c03;
  border-radius: 0.25rem;
  transition: 0.5s;
}

.categorie-list i {
  font-size: 2em;
}

.categorie-list i:hover {
  color: #ff5c03;
  transition: 0.5s;
}
</style>
