<template>
    <cmp-table :items="items" :columns="columns"/>
  </template>
  
<script>
  export default {
    name: 'page',
    data() {
      return {
        items: [ 
          { id: 1, name: 'Sony' } , 
          { id: 2, name: 'Apple' }, 
          { id: 3, name: 'Samsung' } ],
        columns: [ 
          { prop: 'id', title: 'ID' }, 
          { prop: 'name', title: 'Name' } ]
      }
    }
  }
</script>