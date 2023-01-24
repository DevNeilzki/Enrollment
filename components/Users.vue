<template>
  <body style="background-image: url('https://wallpaperaccess.com/full/5923902.jpg'); background-size: cover;">
      <div>
     <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#"><NuxtLink to="/Home" style="color: inherit;text-decoration: none;">Home</NuxtLink></b-navbar-brand>
 

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#"><NuxtLink to="/Dashboard" style="color: inherit;text-decoration: none;">Dashboard</NuxtLink></b-nav-item>
        <b-nav-item href="#"><NuxtLink to="/users" style="color: inherit;text-decoration: none;">Add Student</NuxtLink></b-nav-item>
        <b-nav-item href="#"><NuxtLink to="/Contact" style="color: inherit;text-decoration: none;">Contact</NuxtLink></b-nav-item>
        <b-nav-item href="#"><NuxtLink to="/About" style="color: inherit;text-decoration: none;">About</NuxtLink></b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
        </b-nav-form>

        <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item href="#">EN</b-dropdown-item>
          <b-dropdown-item href="#">ES</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">FA</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template #button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#" ><NuxtLink to="/" style="color: inherit;text-decoration: none;">Sign Out</NuxtLink></b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
      </b-collapse>
        </b-navbar>
    </div>
    <div class="form-inline" action="#">
      <input type="text" id="FirstName" v-model="item.firstname" placeholder="First Name" class="form-control">
      <input type="text" id="LastName" v-model="item.lastname" placeholder="Last Name" class="form-control">
      <button @click="addItem" id="AddUser" class="btn btn-dark"><i class="fas fa-plus">Add</i></button>
        </div>
        <table id="UserTable" class="table table-striped table-bordered table-sm" style="color: white; background-color: palevioletred;">
        <thead class="thead-light">
          <th>First Name</th>
          <th>Last Name</th>
          <th class="col-2">Edit/Delete</th>
        </thead>
        <tr v-for="item in items" :key="item.firstname">
          <td>
            <input v-if="item.edit" type="text" v-model="item.firstname">
            <span v-else>{{item.firstname}}</span>
          </td>
          <td>
            <input v-if="item.edit" type="text" v-model="item.lastname">
            <span v-else>{{item.lastname}}</span>
          </td>
          <td><button @click="ItemEdit(item)" class="btn btn-info"><i class="far fa-edit">edit</i></button>
            <button @click="removeItem(item)" class="btn btn-danger"><i class="far fa-trash-alt">delete</i></button></td>
        </tr>
      </table>
  </body>
  
  </template>
  

  <style scoped>
  .form-inline input {
    margin-right:8px;
  }
  </style>

  <script scope>
  let url = "http://localhost:3002/users";
    export default {
      data() {
      return {
        item: {id: 0, firstname: "", lastname: "", edit: false},
        items: [],
        tempData: []
      }
    },
    methods:{
      async addItem() {
        console.log(this.item.id);
        await this.$axios.$post(url + '/insert', this.item)
        .then((res) => {
          console.log(res);
          this.item = {id: "0", firstname: "", lastname: "", edit: false};
        })
        .catch((err) => console.log(err));
        this.GetAllData();
        this.GetCurrentID();
      },
      async removeItem(item){
        await this.$axios.$post(url + '/delete', {id: item.id})
        .then((res) => {
          console.log(res);
          this.GetAllData();
      })
      .catch((err) => console.log(err));
      },
      async GetAllData(){
        this.items = await this.$axios.$get(url)
        .then((res) => {
          console.log(res);
          this.tempData = res;
          console.log(this.items);
        })
        .catch((err) => console.log(err));
        this.items = this.tempData;
        this.GetCurrentID();
      },
      async ItemEdit(item) //For Updating
      {
        if(!item.edit)
        {
          item.edit = !item.edit
        }
        else
        {
          item.edit = !item.edit
          console.log(item);
          await this.$axios.$post(url + '/update', item)
          .then((res) => {
            console.log(res);
          })
          .catch((err) => console.log(err));
        }
      },
      GetCurrentID(){
        this.item.id = Math.max.apply(Math, this.items.map(function(o) { return o.id; })) + 1;
      }
    },
    async mounted(){
      await this.GetAllData();
    }
  }
  </script>
  

  
  