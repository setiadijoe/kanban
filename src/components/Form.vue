<template>
  <div class="container">
    <div class="col-sm-1">

    </div>
    <div class="col-sm-10">
      <form>
        ADD TASK
        <div class="form-group">
          <input type="text" id="title" v-model="title" placeholder="Insert the Title">
        </div>
        <div class="form-group">
          <textarea id="description" cols="32" rows="3" v-model="description" placeholder="Input description"></textarea>
        </div>
        <div class="form-group">
          <input type="number" id="number" v-model="number" placeholder="0000">
        </div>
        <button type="submit" class="btn btn-primary" v-on:click="addTask()">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Formulir',
  data () {
    return {
      title: '',
      description: '',
      number: 0
    }
  },
  methods: {
    addTask () {
      this.$db.ref('kanban/backlog/').push({
        title: this.title,
        description: this.description,
        number: this.number
      })
      this.title = ''
      this.description = ''
      this.number = 0
    }
  }
}
</script>

<style>

</style>
