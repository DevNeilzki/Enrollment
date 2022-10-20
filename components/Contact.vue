<template>
  <body style="background-image: url('https://wallpaperaccess.com/full/5923902.jpg'); background-size: cover;">
    <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#"><NuxtLink to="/Home" style="color: inherit;text-decoration: none;">Home</NuxtLink></b-navbar-brand>
 

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#"><NuxtLink to="/Dashboard" style="color: inherit;text-decoration: none;">Dashboard</NuxtLink></b-nav-item>
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
    <b-card bg-variant="light" style="max-width: 540px; margin: auto; margin-top: 15%;" class="text-center">
    <b-form-group
      label-cols-lg="3"
      label="Send an Email"
      label-size="lg"
      label-class="font-weight-bold pt-0"
      class="mb-0"
    >
      <b-form-group
        label="Street:"
        label-for="nested-street"
        label-cols-sm="3"
        label-align-sm="right"
      >
        <b-form-input id="nested-street"></b-form-input>
      </b-form-group>

      <b-form-group
        label="City:"
        label-for="nested-city"
        label-cols-sm="3"
        label-align-sm="right"
      >
        <b-form-input id="nested-city"></b-form-input>
      </b-form-group>

      <b-form-group
        label="State:"
        label-for="nested-state"
        label-cols-sm="3"
        label-align-sm="right"
      >
        <b-form-input id="nested-state"></b-form-input>
      </b-form-group>

      <b-form-group
        label="Country:"
        label-for="nested-country"
        label-cols-sm="3"
        label-align-sm="right"
      >
        <b-form-input id="nested-country"></b-form-input>
      </b-form-group>
      <b-form-group
        label="Concern:"
        label-for="nested-country"
        label-cols-sm="3"
        label-align-sm="right"
      >
      <b-form-textarea
        id="textarea-rows"
        placeholder="Tall textarea"
        rows="8"
      ></b-form-textarea>
      </b-form-group>
    </b-form-group>
  </b-card>
  </body>
  
  </template>