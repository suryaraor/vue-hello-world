<template>
  <div class="hello">
    <h1>{{ info }}</h1>
    
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    apiUrl: String
  },
  data() {
    return {
      info: 'vue JS'
    }
  },
  mounted () {
    axios.defaults.baseURL = 'http://129.213.117.177:8081';
    axios
      .get('/name')
      .then(response => (this.info = response.data))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
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
}
</style>
