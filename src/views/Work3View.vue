<template>
  <div class="work3">
    <ul>
      <li v-for="(item, index) in list" :key="index">Name: {{item.name}} / City: {{item.city}}</li>
    </ul>
    <table>
      <thead>
        <th>Name</th>
        <th>City</th>
      </thead>
      <tbody>
        <tr v-for="(item, index) in list" :key="index">
          <td>{{item.name}}</td>
          <td>{{item.city}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style lang="scss">
  ul {
    li {
      list-style: none;
      margin: 10px;
    }
  }
  table {
    margin: 30px auto 0;
  }
  table,th,td {
    width: 250px;
    border-collapse:collapse;
    border: 2px solid #3f51b5;
    th {
      height: 30px;
      background-color: #3f51b5;
      color: white;
    }
    tr {
      height: 30px;
    }
  }
</style>
<script>

export default {
  name: 'Work3View',
  data () {
    return {
      list: []
    }
  },
  mounted () {
    this.getList()
  },
  methods: {
    getList: function () {
      fetch('https://mocki.io/v1/d4867d8b-b5d5-4a48-a4ab-79131b5809b8')
        .then((res) => res.json())
        .then((res) => {
          this.list = res
        })
    }
  }
}
</script>
