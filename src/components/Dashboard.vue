<template>
  <div class="dashboard">
    <div class="banner">
      <div class="menu-btn" v-on:click="toggle('menu')" :class="[toggleMenu ? 'change' : '']">
        <div class="column1">
          <div class="dot"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>
        <div class="column2">
          <div class="dot"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>
        <div class="column3">
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
      <div class="left_expander" v-on:click="toggle('left')" :class="[toggleLeft ? 'change' : '']">
        <div class="bar1"></div>
        <div class="bar2"></div>
        <div class="bar3"></div>
      </div>
      <div class="file_dropdown" v-on:click="toggle('file')" :class="[toggleFile ? 'display' : '']">
        File ﹀
        <div class="dropdown-content">
          <a href="#">Item 1</a>
          <a href="#">Item 2</a>
          <a href="#">Item 3</a>
        </div>
      </div>
      <div class="file_dropdown" v-on:click="toggle('view')" :class="[toggleView ? 'display' : '']">
        View ﹀
        <div class="dropdown-content">
          <a href="#">Item 1</a>
          <a href="#">Item 2</a>
          <a href="#">Item 3</a>
        </div>
      </div>
    </div>

    <div class="main_window">
      <div class="menu_display" :class="[toggleMenu ? 'display' : '']">
        <div class="header">Menu Stuff</div>
        <div class="menu_item">Item 1</div>
        <div class="menu_item">Item 2</div>
        <div class="menu_item">Item 3</div>
      </div>
      <div class="left_panel" :class="[toggleLeft || toggleMenu ? 'left_expanded' : '']">
          <div class="left_item_mini"  :class="[toggleLeft ? 'hide' : 'display']">Item</div>
          <div class="left_item_large" :class="[toggleLeft ? 'display' : 'hide']">Item Extended</div>
          <div class="left_item_mini" :class="[toggleLeft ? 'hide' : 'display']">Item</div>
          <div class="left_item_large" :class="[toggleLeft ? 'display' : 'hide']">Item Extended</div>
          <div class="left_item_mini" :class="[toggleLeft ? 'hide' : 'display']">Item</div>
          <div class="left_item_large" :class="[toggleLeft ? 'display' : 'hide']">Item Extended</div>
          <div class="left_item_mini" :class="[toggleLeft ? 'hide' : 'display']">Item</div>
          <div class="left_item_large" :class="[toggleLeft ? 'display' : 'hide']">Item Extended</div>
      </div>
      <div class="content_container">
        <div class="content">Content view</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dashboard",
  data() {
    return {
      toggleMenu: false,
      toggleLeft: false,
      toggleFile: false,
      toggleView: false
    };
  },
  methods: {
    toggle: function(choice) {
      switch (choice) {
        case "menu":
          !this.toggleMenu
            ? (this.toggleMenu = true)
            : (this.toggleMenu = false);
          break;
        case "left":
          !this.toggleLeft
            ? (this.toggleLeft = true)
            : (this.toggleLeft = false);
          break;
        case "file":
          !this.toggleFile
            ? ((this.toggleFile = true), (this.toggleView = false))
            : (this.toggleFile = false);
          break;
        case "view":
          !this.toggleView
            ? ((this.toggleView = true), (this.toggleFile = false))
            : (this.toggleView = false);
          break;
      }
    }
  }
};
</script>

<style scoped>
.dashboard {
    height: 100%;
    width: 100%;
}
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
  height: 100%;
}

.left_panel {
  display: inline-block;
  background-color: #333333;
  width: 32px;
  height: 100%;
}

.left_expanded {
   width: 145px; 
}

.left_item_mini {
    padding: 0 2px 2px 4px;
    font-size: 10px;
    background-color: #212121;
}

.left_item_large {
    padding: 4px 2px 5px 18px;
    font-size: 10px;
    background-color: #212121;
}

.content_container {
  display: inline-block;
  background-color: white;
  width: 100%;
  height: 100%;
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

.menu_display {
    position: absolute;
  display: none;
  width: 130px;
  height: 100%;
  background-color: #f2c812;
}

.header {
  color: #000000;
  border-bottom: 1px solid black;
  margin: 0 10px 5px 10px;
  font-weight: bold;
}

.menu_item {
  color: #000000;
  margin: 0 10px 5px 10px;
  font-size: 14px;
}

.menu_item:hover {
  color: #000000;
  margin: 0 10px 5px 10px;
  font-weight: bold;
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

.column1,
.column2,
.column3 {
  margin-top: 10px;
  transition: 0.4s;
}

.dot {
  background-color: black;
  height: 3px;
  width: 3px;
  margin-right: 2px;
  margin-bottom: 1px;
}

.left_expander {
  display: inline-block;
  cursor: pointer;
  padding-left: 6px;
  padding-top: 5px;
}

.bar1,
.bar2,
.bar3 {
  width: 16px;
  height: 1px;
  background-color: white;
  margin: 4px 0;
  transition: 0.4s;
}

/* Rotate first bar */
.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-5px, 4px);
  transform: rotate(-45deg) translate(-5px, 4px);
}

/* Fade out the second bar */
.change .bar2 {
  opacity: 0;
}

/* Rotate last bar */
.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-3px, -3px);
  transform: rotate(45deg) translate(-3px, -3px);
}

.change .column1 {
  -webkit-transform: rotate(60deg) translate(1px, -1px);
  transform: rotate(45deg) translate(1px, -1px);
}

/* Fade out the second bar */
.change .column2 {
  opacity: 0;
}

/* Rotate last bar */
.change .column3 {
  -webkit-transform: rotate(-45deg) translate(0px, -2px);
  transform: rotate(-45deg) translate(0px, -2px);
}

.file_dropdown {
  position: relative;
  display: inline-block;
  margin-left: 18px;
  font-size: 10px;
  margin-top: 10px;
  cursor: pointer;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #333333e3;
  min-width: 50px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
  padding-left: 6px;
}

.dropdown-content a {
  color: white;
  padding: 5px 6px;
  text-decoration: none;
  display: block;
  font-size: 10px;
}

.hide {
  display: none;
}

.display {
  display: block;
}

.display .dropdown-content {
  display: block;
}

.expand_left {
    display: block;
}
</style>