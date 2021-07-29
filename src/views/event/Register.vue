<template>
  <p>Regstration form here</p>
  <button @click="register">Register Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'], // <--- Inject the Global Store
  methods: {
    register() {
      //Assuming successful API call to register them

      //Set a flash message to appear on the next page loaded which says
      // 'You are succesfully registerd for ' + this.event.title

      this.GStore.flashMessage = 'You are successfully registered for ' + this.event.title
      setTimeout(() => {
        //After 3 second remove it
        this.GStore.flashMessage = ''
      }, 3000)
// Set a flash message to appear on the next page loaded which says

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
