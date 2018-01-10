<template>
    <div class="container app-container is-fluid">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      <!-- Listening to your own method -->
      <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
      <div class="columns is-centered">
        <div class="column">
          <span class="tag is-warning is-medium">Info: Click on a quote to delete it.</span>
        </div>
      </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';
    export default {
      data: function(){
        return{
          quotes: [
            'This is the test quote.'
          ],
          maxQuotes: 10
        }
      },
      methods: {
        newQuote(quote){
          if(this.quotes.length >= this.maxQuotes){
            return alert('Please delete a quote before adding more.');
          }
          this.quotes.push(quote);
        },
        deleteQuote(index){
          // Splice - at the index position in the array remove one element.
          this.quotes.splice(index, 1);
        }
      },
      components: {
        appQuoteGrid: QuoteGrid,
        appNewQuote: NewQuote,
        appHeader: Header
      }
    }
</script>

<style>
.container.app-container
{
  padding-left: 32px;
  padding-right: 32px;
  max-width: 950px;
  margin: 0 auto;
}
</style>
