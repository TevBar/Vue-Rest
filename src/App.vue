
<template>
  <div>
    <router-view/>
  </div>
</template>



<script>
  export default { 
    name: 'App',
  }
</script>

<style>
#app{ 
  text-align: center; 
}
body{
  padding:0;
  margin:0;
}
.logo{ 
  width: 100px; 
}


.register input, .add input{
    width: 300px;
    height: 50px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border: 1px solid skyblue;
}
.register button, .add button { 
    width: 320px;
    height: 50px;
    border: 1px solid skyblue;
    background-color: skyblue;
    cursor: pointer;
}
.login input {
    width: 300px;
    height: 50px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border: 1px solid skyblue;
}
.login button { 
    width: 320px;
    height: 50px;
    border: 1px solid skyblue;
    background-color: skyblue;
    cursor: pointer;
}
</style> 


