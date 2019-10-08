<template>
  <header>
    <nav
      class="navbar fixed-top navbar-toggleable-md navbar-expand-lg scrolling-navbar double-nav"
    >
      <div class="breadcrumb-dn mr-auto">
        <p class="brand">[INSIDE]</p>
      </div>
      <ul class="nav navbar-nav nav-flex-icons ml-auto">
        <li class="nav-item">
          <a class="nav-link">
            <i class="fas fa-tachometer-alt"></i>
            <span class="clearfix d-none d-sm-inline-block">
              Dashboard
            </span>
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link">
            <i class="fas fa-envelope"></i>
            <span class="clearfix d-none d-sm-inline-block">
              All Newsletters
            </span>
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link">
            <i class="fas fa-comments"></i>
            <span class="clearfix d-none d-sm-inline-block">
              My Newsletters
            </span>
          </a>
        </li>
        <li class="nav-item dropdown">
          <a
            class="nav-link dropdown-toggle"
            href="#"
            id="navbarDropdownMenuLink"
            data-toggle="dropdown"
            aria-haspopup="true"
            aria-expanded="false"
          >
            Welcome {{ this.$store.state.user.name }}
          </a>
          <div
            class="dropdown-menu dropdown-menu-right"
            aria-labelledby="navbarDropdownMenuLink"
          >
            <a class="dropdown-item" href="#">My Profile</a>
            <a class="dropdown-item" href="#">Settings</a>
            <a class="dropdown-item" href="#">Sign out</a>
          </div>
        </li>
      </ul>
    </nav>
  </header>
</template>
<script>
export default {}
</script>
<style scoped>
nav {
  background: #ff5c03;
}
.brand {
  font-size: 2em;
  font-weight: 800;
  color: #fff;
}
.nav-item {
  color: #fff;
  font-size: 1.2em;
}
.dropdown {
  font-weight: 800;
}
.nav-link {
  color: #fff;
}
</style>
