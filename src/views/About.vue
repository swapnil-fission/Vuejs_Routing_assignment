<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Sidemenu/>
    <Header/>
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import Sidemenu from '../components/Sidemenu.vue'
export default {
  name: 'About',
  components: {
    Header,
    Sidemenu
  }
}
</script>
