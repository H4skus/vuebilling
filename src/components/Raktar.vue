<template>
  <div class="data">
      <table>
          <th>
              Title
          </th>
          <th>
              Price
          </th>
          <th>
              Quantity
          </th>
          <th>
              Operations
          </th>
          <th>
              Final Results
          </th>
          <RaktarItem
          v-for="row in rows"
          v-bind:key="row.title"
          :row="row"
          @raktar-item-changed="Changed"
          @raktar-item-delete="Delete"
          />
          <tr>
              <td>
                <input type="text" v-model="title" placeholder="Title">
              </td>
              <td>
                  <input type="number" v-model="price" placeholder="Price">
              </td>
              <td>
                  <input type="number" v-model="quantity" placeholder="Quantity">
              </td>
              <td>
                  <button @click="Post"> Add</button>
              </td>
          </tr>
      </table>
  </div>
</template>

<script>
import RaktarItem from './RaktarItem.vue'
export default {
    props: ['rows'],
    components: {RaktarItem},
    methods: {
        Changed(e) {
            this.$emit('raktar-item-changed', e)
        },
        Post(){
            this.$emit('raktar-item-post', {
                new:{
                    title:this.title,
                    price:this.price,
                    quantity:this.quantity
                }
            })
            this.title="",
            this.price=null,
            this.quantity=null
        },
        Delete(e){
            this.$emit('raktar-item-delete', e)
        }
    }
}
</script>

<style>
body{
  background-color: aquamarine;
  font-family: Georgia, 'Times New Roman', Times, serif;
  position: absolute;
  right: 500px;
  left: 500px;
  top:  200px;
}
.data{
  border-style: solid;
  border-radius: 18px;
  background-color: blanchedalmond;
}

</style>
