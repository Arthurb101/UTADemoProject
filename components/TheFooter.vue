<template>
  <footer>
    <p class="footerText" >careers</p>
    <p class="footerText" >stuff</p>
    <p class="footerText" >more stuff</p>
  </footer>
</template>
<script>


export default {
  name: 'TheFooter',
  components: {


  }
}
</script>
<style>
footer {
  border-top: 1px solid #eee;
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  text-align: center;
}

.footerText{
  display:inline;
  margin-right: 80px;
}
</style>
