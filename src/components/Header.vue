<template>
  <div>
    <div class='header'>
      <h1>Header</h1>
      <p>My supercool header</p>
    </div>

    <div class='content'>
      <h1>Content</h1>
      <p>Some content blablabla, some content blablabla.</p>
      <p>Some content blablabla, some content blablabla.</p>
      <p>Some content blablabla, some content blablabla.</p>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
body {
  font-family: Arial;
  margin: 0;
}
.header {
  padding: 30px;
  text-align: center;
  background: #1abc9c;
  color: white;
  font-size: 20px;
}
.content {
  padding: 20px;
}
</style>
