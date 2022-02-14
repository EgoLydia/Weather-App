<template>
  <div id="app"></div>
</template>

<script>
export default {
  name: 'app'
  data(){
    return{
      api_key: '582f58018e28370809832a36ffc87799'
    }
}
</script>

<style lang='scss' scoped>

  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}

.search-box .search-bar:focus{
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
    border-radius: 16px 0px 16px 0px;

}
</style>
