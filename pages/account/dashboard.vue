<template>
  <div>
    <div class="mb-5">
      <dashboardnav />
    </div>
    <div class="container p-5">
      <div class="mt-5">
        <dashboardprincipal />
      </div>
    </div>
  </div>
</template>
<script>
import dashboardnav from '@/components/dashboard-nav'
import dashboardprincipal from '@/components/dashboard-principal'
export default {
  middleware: 'loggedin',
  layout: 'dashboard_layout',
  components: {
    dashboardnav,
    dashboardprincipal
  }
}
</script>
