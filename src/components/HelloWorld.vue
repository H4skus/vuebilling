<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  <div class="table">
    <table>
      <th>
        title
      </th>
        price
      <th>
        quantity
      </th>
      <tr>
        <Items>
        </Items>
      </tr>
    </table>
  </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.table{
  align-items: center;
  text-align: center;
  position: absolute;
}
</style>
