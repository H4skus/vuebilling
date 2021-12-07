<template>

<ul id="App">
  <li v-for="(title, price, quantity) in rows">
    {{ title }} -- {{ price }} -- {{ quantity }}
  </li>
</ul>
</template>


<script>

</script>
