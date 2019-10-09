<template>
  <div class="hello">
    <a-alert :message=this.msg() type="info" closeText="x"/>

    <!-- here is the show begin -->
  </div>
</template>

<script>
export default {
  name: 'BaseGenSet',
  props: {
    msg: String
  },
  methods: {
    showMessage () {
      return this.msg || ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>
