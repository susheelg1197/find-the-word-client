<template>
  <mdb-navbar expand="large" class="nav-b">
      <div class="container-fluid">
      <h1 class="text-right">Find the Word!</h1>
      </div>
    
  </mdb-navbar>
</template>
<script>
  import { mdbNavbar} from 'mdbvue';
  export default {
    name: 'NavbarPage',
    components: {
      mdbNavbar
    }
  }
</script>
<style scoped>
.nav-b{
    background-color:#5755d9 ;
    color:white;
}
</style>