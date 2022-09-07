<template>
    <div>
        <h1>Bennedito Muianga</h1>
    </div>
</template>


<script>
    export default {
        name:'Footer',
    }
</script>

<style scoped>
  div{
    width: 100%;
    position: fixed;
    bottom: 0;
    background-color: #3c1c6628;
  }
  h1{
    font-style: oblique;
    padding-top: 5px;
    text-align: center;
    font-size: 20px;
  }

  @media only screen and (max-width: 900px) {
    div{
      margin-top: 20px;
      position:relative;
      margin-bottom: -10px;
    }
  }

  @media only screen and (max-width: 750px) {
    h1{color:white}
  }
</style>