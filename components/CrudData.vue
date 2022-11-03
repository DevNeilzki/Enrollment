<template>
  <body style="background-image: url('https://wallpaperaccess.com/full/5923902.jpg'); background-size: cover;">
    <div class="form-inline" action="#">

      <b-button id="toggle-btn" variant="primary" @click="showModal" style="margin: 20px 0 0 20px">Add Students</b-button>

      <b-modal ref="my-modal" hide-footer title="Add New Student">
      <div class="d-block text-center">
        <b-form-input type="text"  v-model="item.fname" placeholder="First Name" id="validationDefault01" required class="form-control" style="margin-top: 10px" ></b-form-input>
        <b-form-input type="text"  v-model="item.lname" placeholder="Last Name" id="validationDefault02" required class="form-control" style="margin-top: 10px" ></b-form-input>
        <b-form-input type="text"  v-model="item.addrss" placeholder="Address" id="validationDefault04" required class="form-control"  style="margin-top: 10px"></b-form-input>
        <b-form-input type="text"  v-model="item.schl" placeholder="School" class="form-control" style="margin-top: 10px" ></b-form-input>
    <input type="number" v-model="item.num" placeholder="Contact Number" class="form-control" id="validationDefault05" required style="margin-top: 10px" v-on:keyup.enter="addItem">
      </div>
      <b-button class="mt-3" variant="outline-danger" block  @click="addItem" >Add Student</b-button>
      <b-button class="mt-2" variant="outline-warning" block @click="hideModal">Close</b-button>
    </b-modal>
      </div>
    <br><br>
    <table class="table table-striped table-bordered table-sm, text-center" style="color: white; background-color: palevioletred;">
      <thead>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Address</th>
        <th>School</th>
        <th>Contact Number</th>
        <th class="col-2">Action</th>
      </thead>
      <tr v-for="item in items" :key="item.name">
        <td>
          <input v-if="item.edit" type="text" v-model="item.fname"  v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.fname}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.lname"  v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.lname}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.addrss"  v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.addrss}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.schl"  v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.schl}} </span>
        </td>
        <td>
          <input v-if="item.edit" type="text" v-model="item.num" v-on:keyup.enter="item.edit = !item.edit">
          <span v-else>{{item.num}} </span>
        </td>
        <td>
          <b-button  @click="item.edit = !item.edit" class="btn btn-info">Edit</b-button>
          <b-button   @click="removeItem(index)" class="btn btn-danger">Delete</b-button>
        </td>
      </tr>
    </table>
  </body>
  </template>
  
  <script>
    export default {
      data() {
        return {
        item: {fname: "", lname: "", addrss: "", schl: "", num: "", edit: false},
        items: []
        }
      },
      methods:{
    addItem() {
      this.items.push({
        fname:this.item.fname, lname:this.item.lname, addrss:this.item.addrss, schl:this.item.schl, num:this.item.num, edit: false}
        );
      this.item = [];
        },
    removeItem(index){
      this.items.splice(index, 1)
    },  
    showModal() {
        this.$refs['my-modal'].show()
      },
      hideModal() {
        this.$refs['my-modal'].hide()
      }
      }
    }
  </script>
  
  <style>
 .form-inline input {
  margin-right:8px;
}  
  </style>