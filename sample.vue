<template>
  <body>
  <div id="app">
    <h1>{{ message }}</h1>
    <div>検索：<input type="text" v-model="search"></div>
    <table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Website</th>
        </tr>
    </thead>
    <tbody>
        <tr v-for="user in search_users" :key="user.id">
            <td>{{ user.name }}</td>
            <td>{{ user.email }}</td>
            <td>{{ user.website }}</td>
        </tr>
    </tbody>
    </table>
  </div>
  </body>
</template>

<script>
export default{
  data(){
    return {
    message: 'Search/Filter In Table',
    users:[],
    search:""
    };
  },
  mounted(){
    axios.get('https://jsonplaceholder.typicode.com/users')
          .then(response => this.users = response.data)
  },
  computed: {
    search_users(){
      let searchWord = this.search.trim()
      if (searchWord === '') return this.users;
    　return this.users.filter(user => {
        return user.name.includes(this.search) ||
        user.email.includes(this.search) ||
        user.website.includes(this.search)
    　})
    },
  }
}
</script>