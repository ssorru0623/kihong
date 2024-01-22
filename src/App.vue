<template>
  <h4 style="font-size:100px; color: #000000">
    PathFinder
  </h4>
  <div class="logo">
    <div class="box">
      <div class="container">
        <a>
          {{SearchData}}
        </a>
        <div class="search-container">
          <button @click= "login" class = "login-button" type="submit">
            로그인
          </button>
    <input    
      class= "search-input" 
      type= "text"
      placeholder="Search. . ."
      v-model="SearchData"
      />
    <button @click= "search" class = "search-button" type="submit">
      검색 
      </button>
      </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      SearchData : ""
    }
  },
 methods : {
  search(){
    this.$axios
    .post("/dining",this.SearchData)
    .then(() => {})
    .catch(function(error){
      alert(error);
    });
  }
 }, 
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.search-input{
  display: block;
  padding: 4px 8px;
  margin-right: 10px;
  width: 500px;
  font-size: 16px;
  outline: none;
  
}
body{
  background-image: url("https://www.baemin.com/_next/static/media/main_05@2x.460fb801.jpg");
  background-size: cover;
}
.box{
  margin: 100px auto;
  width: 500px;
  height: 50px;
}

.search-container{
  display: flex; /* 플렉스 레이아웃을 사용하여 아이템을 가로로 배치 */
  align-items: center; /* 아이템을 수직으로 가운데 정렬 */
  position: absolute;
  top: 50%;
  margin-left: -30px;
  
}
button{
  margin-left: 10px;
}
.search-button{
  white-space: nowrap;
}
.logo-img{
  width: auto;
  height: auto;
  object-fit: contain;
}
.login-button{
  position: fixed;
  top: 20px;
  right: 20px;
}
</style>
