<template>
  <div class="columns">
    <form style="width: 100%;">
      <div class="column">
        <label>Add a Quote:</label>
        <textarea class="textarea" row="3" v-model="quote" placeholder="Type your quote here..."></textarea>
        <!-- Prevent overrides default behaviour. In this case does not submit the form to the server. -->
        <button class="button is-link quote-send is-default" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>
<script>
  export default{
    data: function(){
      return{
        quote: ''
      };
    },
    methods: {
      createNew(){
        this.$emit('quoteAdded', this.quote);
        // Clears the form.
        this.quote = '';
      }
    }
  }
</script>
<style>
.quote-send{
  margin-top: 10px;
  float: right;
}
</style>
