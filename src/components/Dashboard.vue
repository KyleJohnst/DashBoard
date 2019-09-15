<template>
  <div class="dashboard">
    <div class="banner">
      <div class="menu-btn">
        <div class="column">
          <div class="dot"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>
        <div class="column">
          <div class="dot"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>
        <div class="column">
          <div class="dot"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>
      </div>
      <div class="banner_name">Chameleon</div>
      <div class="navigation">My Workspace</div>
      <div class="pointer">></div>
      <div>
        <div class="navigation_location">Dashboard</div>
      </div>
    </div>
    <div class="control_panel">
      <div class="container" onclick="myFunction(this)">
        <div class="bar1"></div>
        <div class="bar2"></div>
        <div class="bar3"></div>
      </div>
    </div>
    <div class="main_window">
      <div class="left_panel">left</div>
      <div class="content_container">
        <div class="content">Content view</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dashboard"
};
</script>

<style scoped>
.banner {
  display: flex;
  background-color: #000000;
  width: 100%;
  height: 2em;
}

.banner_name {
  display: inline-block;
  padding-top: 4px;
  padding-left: 5px;
}

.control_panel {
  display: flex;
  background-color: #333333;
  width: 100%;
  height: 30px;
}

.main_window {
  display: flex;
}

.left_panel {
  display: inline-block;
  background-color: #212121;
  width: 32px;
}

.content_container {
  display: inline-block;
  background-color: white;
  width: 100%;
  height: 500px;
  background-color: #eaeaea;
}

.content {
  margin: 0 5% 0 5%;
  background-color: white;
  height: 100%;
}

.menu-btn {
  display: flex;
  justify-content: center;
  background-color: #f2c812;
  width: 30px;
  height: 100%;
  padding-left: 1px;
  cursor: pointer;
}

.navigation {
  display: inline-block;
  padding-top: 9px;
  padding-left: 20px;
  font-size: 10px;
  cursor: pointer;
}

.navigation_location {
  display: inline-block;
  padding-top: 10px;
  padding-left: 5px;
  font-size: 10px;
  cursor: pointer;
}

.pointer {
  display: inline-block;
  padding-top: 7px;
  padding-left: 6px;
  margin-right: 0;
  font-size: 13px;
}

.column {
  margin-top: 10px;
}

.dot {
  background-color: black;
  height: 3px;
  width: 3px;
  margin-right: 2px;
  margin-bottom: 1px;
}

.container {
  display: inline-block;
  cursor: pointer;
  padding-left: 6px;
  padding-top: 5px;
}

.bar1, .bar2, .bar3 {
  width: 16px;
  height: 1px;
  background-color:white;
  margin: 4px 0;
  transition: 0.4s;
  
}

/* Rotate first bar */
.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-9px, 6px) ;
  transform: rotate(-45deg) translate(-9px, 6px) ;
}

/* Fade out the second bar */
.change .bar2 {
  opacity: 0;
}

/* Rotate last bar */
.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-8px, -8px) ;
  transform: rotate(45deg) translate(-8px, -8px) ;
}
</style>