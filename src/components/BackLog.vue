<template>
  <div class="col-md-3">
    <div class="utama">
      <h3>Start</h3>
    </div>
    <div v-for="data in backlog">
      <div>
        <table>
          <tr>
            <td>title :</td>
            <td>{{ data.title }}</td>
          </tr>
          <tr>
            <td>description :</td>
            <td>{{ data.description }}</td>
          </tr>
          <tr>
            <td>number :</td>
            <td>{{ data.number }}</td>
          </tr>
          <tr>
            <br>
          </tr>
          <tr>
            <td><button type="button" @click="deleting(data['.key'])">Delete</button></td>
            <td><button type="button" @click="moveToDo(data['.key'], data.title, data.description, data.number)">Go Todo</button> </td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BackLog',
  data () {
    return {}
  },
  firebase: function () {
    return {
      backlog: this.$db.ref('kanban/backlog/')
    }
  },
  created () {
    console.log(this.backlog)
  },
  methods: {
    deleting (id) {
      this.$db.ref('kanban/backlog/' + id).remove()
    },
    moveToDo (id, title, description, number) {
      this.$db.ref('kanban/todo/').push({
        title: title,
        description: description,
        number: number
      })
      this.$db.ref('kanban/backlog/' + id).remove()
    }
  }
}
</script>

<style>

</style>
