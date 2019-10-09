<template>
  <div class="BaseGenSet">
    <a-alert v-if="visible" :message=showMessage() type="info" closable closeText="x"/>
    <br/>

    <a-row>
      <a-col :span="6">
        {{ smallTitle }}
      </a-col>
      <a-col :span="18">
        <div v-for="(info, index) of detailInfo" :key="index">
          <small>{{ info.title }}</small>
          <p>{{ info.text }}</p>
        </div>
      </a-col>
    </a-row>
  </div>
</template>

<script>
export default {
  name: 'BaseGenSet',
  data() {
    return {
      visible: true,
    }
  },
  props: {
    alertmsg: {
      type: String,
      default: 'Default alert message here'
    },
    smallTitle: {
      type: String,
      default: 'Default Title Here'
    },
    detailInfo: {
      type: Array,
      default: () => [
        { title: 1, text: 'My journey with Vue' },
        { title: 2, text: 'Blogging with Vue' },
        { title: 3, text: 'Why Vue is so fun' }
      ]
    }
  },
  methods: {
    showMessage () {
      if (this.msg === undefined) {
        this.visible = false;
      } else {
        return this.alertmsg;
      }
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
