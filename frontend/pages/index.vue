<template>
  <div class="container">
    <table class="table" id="table">
    <thead class="thead-dark">
      <tr>
        <th>title</th>
        <th>description</th>
      </tr>
    </thead>

    <tbody>
      <tr v-for='item in items'>
        <th scope="row">{{ item.title }}</th>
        <td>{{ item.description }}</td>
      </tr>         
    </tbody>

</table>
      
  </div>
</template>

<script>
import itemsQuery from '~/apollo/queries/item/items'
export default {
  data(){
    return{
      items: [],
      query: ''
    }
  },
  apollo: {
    items: {
      prefetch: true,
      query: itemsQuery
    }
  },


}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}


</style>
