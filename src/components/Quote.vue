<template>
  <div class="column is-one-third">
    <div class="box quote">
      <div class="content">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
</script>
<style>
  .box{
    font-family: 'Arizonia', cursive;
    font-size: 32px;
    color: #6e6e6e;
  }

  .quote{
    cursor: pointer;
  }

  .quote:hover{
    background-color: #ffe2e2;
  }
</style>
