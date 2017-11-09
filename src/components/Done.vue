<template>
  <div class="col-md-3">
    <div class="utama">
      <h3>Done</h3>
    </div>
    <div v-for="data in done">
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
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Done',
  data () {
    return {}
  },
  firebase: function () {
    return {
      done: this.$db.ref('kanban/done')
    }
  },
  created () {
    console.log(this.done)
  },
  methods: {
    deleting (id) {
      this.$db.ref('kanban/done' + id).remove()
    }
  }
}
</script>

<style>

</style>
