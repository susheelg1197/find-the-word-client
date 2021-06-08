<template>
  <mdb-navbar expand="large" class="nav-b">
      <div class="container-fluid">
      <h1 @click="backToHome()" class="head-er text-right">Find the Word!</h1>
      </div>
    
  </mdb-navbar>
</template>
<script>
  import { mdbNavbar} from 'mdbvue';
  export default {
    name: 'NavbarPage',
    components: {
      mdbNavbar
    },
    methods:{
      backToHome(){
        window.open(window.location.origin,"_self")
      }
    }
  }
</script>
<style scoped>
.head-er{
  cursor: pointer;
}
.nav-b{
    background-color:#5755d9 ;
    color:white;
}
</style>