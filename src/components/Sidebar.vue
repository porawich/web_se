<template>
  <div class="container">
    <div
      class="sidebar-box"
      :class="{ 'w-0': !sidebarOpen, 'w-200': sidebarOpen }"
    >
      <div class="img-box">
        <div class="">
          <img class="img-profile"
            src="https://images.unsplash.com/photo-1633332755192-727a05c4013d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=850&q=50"
          />
        </div>
        <div class="user-info">
            <p>itthikorn wisetpong</p>
            <p>Kasetsart University</p>
        </div>
      </div>
      <router-link class="menu-list py-9" to="/home"
        ><span>Home</span></router-link
      >
      <router-link class="menu-list py-9" to="/about"
        ><span>About</span></router-link
      >
    </div>
    <div style="display: flex; flex-direction: column; width: 100vmax">
      <Navbar @openSidebar="openSidebar" />
      <div class="content-box">
        <router-view />
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "./Navbar.vue";
export default {
  components: {
    Navbar,
  },
  data() {
    return {
      sidebarOpen: true,
    };
  },
  methods: {
    openSidebar(isOpen) {
      // console.log(isOpen)
      this.sidebarOpen = isOpen;
    },
  },
};
</script>

<style>
.container {
  display: flex;
}
.sidebar-box {
  height: 100vh;
  width: 300px;
  background-color: rgb(77, 8, 8);
  display: flex;
  flex-direction: column;
  align-items: center;
  /* justify-content: center; */
  overflow: hidden;
}
.sidebar-box .img-box {
  display: flex;
  flex-direction: column;
  flex: initial;
  width: 300px;
  height: auto;
  min-width: 0;
  border-bottom: 3px solid whitesmoke;
  align-items: center;
  padding: 8px;
  
}
.img-profile{
    display: flex;
    width: 200px;
    height: 200px;
    border-radius: 50%;

}
.user-info{
    color: white;
    
}
.sidebar-box .menu-list {
  display: flex;
  flex-shrink: 0;
  align-items: center;
  justify-content: center;
  flex: initial;
  border-bottom: 2px solid rgb(235, 235, 235);
  color: whitesmoke;

  width: 100%;
}
.sidebar-box .menu-list:hover {
  background-color: rgb(3, 19, 51);
}
.w-0 {
  width: 0px;
  transition: 0.3s;
  animation-duration: 1s;
}
.w-200 {
  width: 300px;
  transition: 0.3s;
  animation-duration: 1s;
}
.content-box {
  padding: 10px;
}
.py-9 {
  padding-top: 9px;
  padding-bottom: 9px;
}
.px-9 {
  padding-right: 9px;
  padding-left: 9px;
}
</style>