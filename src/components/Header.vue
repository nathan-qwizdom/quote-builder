<template>
  <div class="progress-container">
    <div class="content">
      <h3>Quotes Added ({{ quoteCount }}/{{maxQuotes}})</h3>
      <progress class="progress is-link" :value="quoteCount*10" max="100">

      </progress>
    </div>
  </div>
</template>
<script>
 export default{
   props: ['quoteCount', 'maxQuotes']
 }
</script>
<style>
.progress-container{
  margin: 24px 0;
}

progress.progress{
  transition: all 0.8s;
}
</style>
