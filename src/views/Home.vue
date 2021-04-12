<template>
 <div>
   <Computedandwatchers/>
   <h2 class='changebackground'>home components</h2>
 </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import Computedandwatchers from '../components/Computedandwatchers.vue'
@Component({
  components: {
    Computedandwatchers
  }
})
export default class Home extends Vue {}
</script>
<style lang="scss">

.changebackground {
  background-color: blue;
}
</style>
