<template>
  <div id="app"></div>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Search...">
      </div>
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
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-family: Arial, Helvetica, sans-serif;
}
#app {
  background-image: url('./assets/cold-bg.jpg');
  background-size: contain;
  background-position: bottom;
  transition: 0.4s;
}

main{
  min-height: 100vh;
  padding: 25px;
  background-image: linear-gradient(to bottom, rgba(0,0,0,0.25), rgba(0,0,0,0.75));
}

.search-box{
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar{
  display: flex;
  width: 100%;
  padding: 15px;
  color: #313131;
  font-size: 20px;

  appearance: none;
  border: none;
  outline: none;
  background: none;

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
