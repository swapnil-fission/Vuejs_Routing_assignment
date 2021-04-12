<template>
  <div>
    <p>Login Id : </p>
    <input type='text' v-model='loginid' />
    <br />
    <br />
    <p>Password :</p>
    <input type='text' v-model='password' />
    <br />
    <br />
    <h1 class='changecolor'>Login Id {{ loginid }}</h1>
    <h1 class='changecolor'>Password{{ password }}</h1>
    <h2 class='changecolor'>Using Computed Property Id password :-- {{ getIdPass }}</h2>
    <h2 class='changecolor'>Todays Date : {{ todayDate }}</h2>
     Kilometers : <input type = 'text' v-model = 'kilometers'>
     Meters : <input type = 'text' v-model = 'meters'>

     <h2 :class='{green:colorfull,err: true,underline:warning}'>Dynamic classes</h2><br>
     <h2 :class='{green:value>5,err: true,underline:warning}'>{{value}}</h2>
     <button v-on:click='value++'>+</button>
     <button v-on:click='value--'>-</button>
     <button v-on:click='colorfull= !colorfull'>Change color</button>
     <button v-on:click='warning= !warning'>warning</button>
     <h2 :style='{color:colorname}'>Style Binding</h2>
  </div>
</template>
<script>
export default {
  name: 'Computedandwatchers',
  data () {
    return {
      loginid: '',
      password: '',
      kilometers: 0,
      meters: 0,
      value: 1,
      colorfull: true,
      warning: false,
      colorname: 'skyblue'
    }
  },
  computed: {
    getIdPass () {
      return this.loginid + ' ' + this.password
    },
    todayDate () {
      var d = new Date()
      const date = d.toLocaleDateString()
      return date
    }
  },
  watch: {
    kilometers (val) {
      this.kilometers = val
      this.meters = val * 1000
    },
    meters (val) {
      this.meters = val
      this.kilometers = val / 1000
    }
  }
}
</script>
<style lang='scss'>
@mixin textcolor{
  color: red;
  font-size: 30px;
  font-weight: bold;
  padding: 20px;
}

.changecolor {
  @include textcolor;
  background-color: black;
}
p{
  @include textcolor;
}
.green {
  background-color: green;
  width: 200px;
  padding: 12px;
  color: grey;
}
.err {
  color: red;
}
.underline {
  text-decoration: underline;
}

</style>
