<template>
  <div>
    <Form></Form>
      <div>
        <BackLog></BackLog>
        <Doing></Doing>
        <Done></Done>
        <Todo></Todo>
      </div>
  </div>
</template>

<script>
import BackLog from '@/components/BackLog'
import Form from '@/components/Form'
import Doing from '@/components/Doing'
import Done from '@/components/Done'
import Todo from '@/components/Todo'
export default {
  name: 'HelloWorld',
  data () {
    return {
    }
  },
  components: {
    Form,
    BackLog,
    Doing,
    Done,
    Todo
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
