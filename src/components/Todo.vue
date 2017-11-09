<template>
  <div class="col-md-3">
    <div>
      <h3>Todo</h3>
    </div>
    <div v-for="data in todos">
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
            <td><button type="button" @click="moveToDoing(data['.key'],data.title,data.description,data.points)">Do this task</button></td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data () {
    return {}
  },
  firebase: function () {
    return {
      todos: this.$db.ref('kanban/todo/')
    }
  },
  methods: {
    deleting (id) {
      this.$db.ref('kanban/todo/' + id).remove()
    },
    moveToDoing (id, title, description, number) {
      this.$db.ref('kanban/doing').push({
        title: title,
        description: description,
        number: number
      })
      this.$db.ref('kanban/todo' + id).remove()
    }
  }
}
</script>

<style>

</style>
