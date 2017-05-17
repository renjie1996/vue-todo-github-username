<template>
  <div class="new">
    <table>
      <thead>
        <th>webSite</th>
        <th>Acceptability</th>
      </thead>
      <tr>
        <td></td>
        <td>{{github.state}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
  export default {
    props: {
      github: {
        type: Object
      }
    },
    data () {
      return {}
    }
  }
</script>

<style>
  .new {
    margin-top: 40px;
  }
  .new table{
    margin: 0 auto;
  }
</style>
