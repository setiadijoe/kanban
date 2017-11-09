<template>
  <div>
    <Form />
      <div>
        <back-log></back-log>
      </div>
  </div>
</template>

<script>
import BackLog from '@/components/BackLog'
import Form from '@/components/Form'
import Doing from '@/components/Doing'
export default {
  name: 'HelloWorld',
  data () {
    return {
    }
  },
  components: {
    Form,
    BackLog,
    Doing
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
