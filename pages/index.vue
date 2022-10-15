<template>
<body style="background-image: url('https://wallpaperaccess.com/full/5923902.jpg'); background-size: cover;">
  <div   class="fixed-top d-flex align-items-center justify-content-center fadeInDown" style="bottom: 0; overflow-y: auto">
  <b-card  bg-variant="light" style="max-width: 540px;">
    <img src="https://img.icons8.com/external-kiranshastry-lineal-color-kiranshastry/344/external-user-advertising-kiranshastry-lineal-color-kiranshastry-2.png" id="icon" alt="User Icon" />
    <h2 class="text-center"> LOGIN </h2>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Email address:"
        label-for="input-1"
        description="We'll never share your email with anyone else."
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          placeholder="Enter email"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Password:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.name"
          type="password"
          placeholder="Enter Password"
          required
        ></b-form-input>
      </b-form-group>
      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
  </b-card>
</div>
</body>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          email: '',
          name: '',
          food: null,
          checked: []
        },
        show: true
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>

<style>
.fadeInDown {
  animation-name: fadeInDown;
  animation-duration: 2s;}

@keyframes fadeInDown {

  from {  transform: translate3d(0, -50%, 0);}
  to {  transform: translate3d(0, 0, 0);}
}

</style>