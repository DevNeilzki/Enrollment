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
      <b-carousel
        id="carousel-1"
        v-model="slide"
        :interval="4000"
        controls
        indicators
        background="#ababab"
        img-width="1024"
        img-height="250 !important"
        style="text-shadow: 1px 1px 2px #333;"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
  
         <!-- Slides with custom text -->
         <b-carousel-slide  style="height:80vh!important"  img-src="https://images8.alphacoders.com/644/644210.jpg">
          <h1>Hunts Vampires with Incredible Speed, Invulnerability and Enhanced Strength</h1>
        </b-carousel-slide>
  
        <!-- Slides with custom text -->
      <b-carousel-slide  style="height:80vh!important"  img-src="https://coolwallpapers.me/picsup/2968853-vampires-artwork-fantasy-art-anime___anime-wallpapers.jpg">
          <h1>A bloodsucking creature that rises from its burial place at night, sometimes in the form of a bat, to drink the blood of humans.</h1>
        </b-carousel-slide>

        <!-- Slides with custom text -->
        <b-carousel-slide  style="height:80vh!important"  img-src="https://wallpaperaccess.com/full/5695659.jpg">
          <h1>A man who turns into a wolf at night and devours animals, people, or corpses but returns to human form by day</h1>
        </b-carousel-slide>

         <!-- Slides with custom text -->
      <b-carousel-slide  style="height:80vh!important"  img-src="https://img.8wallpapers.com/uploads/2019/03/46f91a76d881422e90be7589.jpg">
          <h1>Vampires are evil mythological beings who roam the world at night searching for people whose blood they feed upon.</h1>
        </b-carousel-slide>
        
      </b-carousel>
      

      <div style="margin-top: 10%">
  <b-card-group deck>
    <b-card title="Title" img-src="https://picsum.photos/300/300/?image=41" img-alt="Image" img-top>
      <b-card-text>
        This is a wider card with supporting text below as a natural lead-in to additional content.
        This content is a little bit longer.
      </b-card-text>
      <template #footer>
        <small class="text-muted">Last updated 3 mins ago</small>
      </template>
    </b-card>

    <b-card title="Title" img-src="https://picsum.photos/300/300/?image=41" img-alt="Image" img-top>
      <b-card-text>
        This card has supporting text below as a natural lead-in to additional content.
      </b-card-text>
      <template #footer>
        <small class="text-muted">Last updated 3 mins ago</small>
      </template>
    </b-card>

    <b-card title="Title" img-src="https://picsum.photos/300/300/?image=41" img-alt="Image" img-top>
      <b-card-text>
        This is a wider card with supporting text below as a natural lead-in to additional content.
        This card has even longer content than the first to show that equal height action.
      </b-card-text>
      <template #footer>
        <small class="text-muted">Last updated 3 mins ago</small>
      </template>
    </b-card>
  </b-card-group>
</div>
    </div>
  </body>
  </template>
  
  <script>
    export default {
      data() {
        return {
          slide: 0,
          sliding: true
        }
      },
      methods: {
        onSlideStart(slide) {
          this.sliding = true
        },
        onSlideEnd(slide) {
          this.sliding = false
        },
      }
    }
  </script>