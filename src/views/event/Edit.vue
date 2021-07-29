<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'], // <--- Inject the Global Store
  methods: {
    edit() {
      //Assuming successful API call to register them

      //Set a flash message to appear on the next page loaded which says
      // 'You are succesfully registerd for ' + this.event.title

      this.GStore.flashMessageEdit = 'The data has been updated'
      setTimeout(() => {
        //After 3 second remove it
        this.GStore.flashMessageEdit = ''
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
