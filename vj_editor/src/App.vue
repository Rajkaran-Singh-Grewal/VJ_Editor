<template>
  <div id="container">
    <div id="header">
      <ul>
        <li>Logo</li>
        <li>File</li>
        <li>Edit</li>
        <li>Selection</li>
        <li>View</li>
        <li>Go</li>
        <li>Run</li>
        <li>Terminal</li>
        <li>Help</li>
      </ul>
    </div>
    <div id="nav">
      <router-link id="explorer_nav" to="/">Explorer</router-link> 
      <router-link to="/about">Search</router-link> 
      <router-link to="/source-control">Git</router-link> 
      <router-link to="/Debugger">Debugger</router-link> 
      <router-link to="/Extensions">Extensions</router-link> 
      <router-link class="cap-3" to=""></router-link>
      <router-link id="setting_nav" to="/Settings">Settings</router-link>
    </div>
    <div id="side-panel">
       <router-view/>
    </div>
    <div id="text-editor">
      <Editor/>
    </div>
    <div id="right-panel"></div>
    <div id="footer"></div>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#container{
  display:grid;
  height: 100vh;
  grid-template-columns: auto;
  grid-template-rows: 20px auto;
  grid-template-areas:
  "header header header header header  header header header header header header header"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "nav    side   side   side   editor  editor editor editor editor right  right  right"
  "footer footer footer footer footer  footer footer footer footer footer footer footer";
  #header{
    grid-area: header;
    background-color: #191919;
    ul{
      display: flex;
      margin: 0px;
      padding: 0px;
      color: white;
      li{
        list-style: none;
        margin-left: 10px;
      }
    }
  }
  #nav{
    grid-area: nav;
    width: 100px;
    background-color: #191919;
    display: grid;
    grid-template-rows: 20px 20px 20px 20px 20px 20px 20px 20px 20px 20px 20px 20px;
    resize: horizontal;
    overflow: auto;
    a{

    }
  }
  #side-panel{
    grid-area: side;
    
  }
  #text-editor{
    grid-area: editor;
  }
  #right-panel{
    grid-area: right;
  }
  #footer{
    grid-area: footer;
  }
}
#navbar {
  display: flex;
  justify-content: flex-start;
  min-height: 100%;
  #nav {
    padding: 30px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    background-color: #2c3e50;
    min-height: 100%;
    height: 100%;
    #setting_nav {
    }
    .cap-3 {
      flex-grow: 4;
    }
    a {
      font-weight: bold;
      color: #ea00ff;

      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }
}
</style>
<script lang="ts">
import Vue from "vue";
import Editor from "./components/editor.vue";
export default {
  name: "NavBar",
  components: {
    Editor
  },
};
</script>