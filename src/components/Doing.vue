<template>
  <div class="col-md-3">
    <div>
      <h3>Doing</h3>
    </div>
    <div v-for="data in Doing">
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
            <td><button type="button" @click="moveToDo(data['.key'], data.title, data.description, data.number)">Done</button> </td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>
