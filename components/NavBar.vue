<template>
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
  </template>