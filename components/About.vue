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
    <b-card  bg-variant="light" style="max-width: 540px; margin: auto" class="text-center">
      <img src="https://img.icons8.com/external-kiranshastry-lineal-color-kiranshastry/344/external-user-advertising-kiranshastry-lineal-color-kiranshastry-2.png"  id="icon" alt="User Icon" />
      <h2 class="text-center"> About US </h2>
      <p class="text-justify">
        "Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam,
         eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem 
         quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. 
         Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora 
         incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis 
         suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse 
         quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur?"
      </p>
    </b-card>
  </body>
  
  </template>