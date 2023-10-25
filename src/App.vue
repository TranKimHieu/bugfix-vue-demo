<template>
  <el-row class="tac">
    <el-col class="sidebar" :span="4">
      <el-row>
        <img src="./assets/logo.svg">
        <h2>Base</h2>
      </el-row>
      <el-menu
        bor
        background-color="#fff"
        class="el-menu-vertical-demo"
        default-active="2"

      >
        <el-menu-item index="1">
          <el-icon><img src="./assets/dashboard.svg"></el-icon>
          <span>Dashboard</span>
        </el-menu-item>
        <el-menu-item index="2">
          <el-icon><img src="./assets/analytics.svg"></el-icon>
          <span>Analytics</span>
        </el-menu-item>
        <el-menu-item index="3">
          <el-icon><img src="./assets/invoice.svg"></el-icon>
          <span>Invoice</span>
        </el-menu-item>
        <el-menu-item index="4">
          <el-icon><img src="./assets/schedule.svg"></el-icon>
          <span>Schedule</span>
        </el-menu-item>
        <el-menu-item index="5">
          <el-icon><img src="./assets/calendar.svg"></el-icon>
          <span>Calendar</span>
        </el-menu-item>
        <el-menu-item index="6">
          <el-icon><img src="./assets/message.svg"></el-icon>
          <span>Messages</span>
          <el-button type="danger" plain>49</el-button>
        </el-menu-item>
        <el-menu-item index="7">
          <el-icon><img src="./assets/notification.svg"></el-icon>
          <span>Notification</span>
        </el-menu-item>
        <el-menu-item index="8">
          <el-icon><img src="./assets/settings.svg"></el-icon>
          <span>Settings</span>
        </el-menu-item>
        <el-col>
          <img alt="object" src="./assets/object.png">
        </el-col>
        <el-col>
          <img alt="vector" src="./assets/Vector 8.svg">
        </el-col>
        <el-button type="primary">Upgrade Now</el-button>
        <el-row>
          <el-icon><img src="./assets/Rectangle 115.png"></el-icon>
          <el-row>
          <el-col>Easin Arafat</el-col>
          <el-col>Free Account</el-col>
          </el-row>
          <el-icon><img src="./assets/logout.svg"></el-icon>
        </el-row>
      </el-menu>
    </el-col>
  </el-row>

  <!-- <el-scrollbar max-height="900px" width="218px">
    <p v-for="item in 8" :key="item" class="scrollbar-demo-item">{{ item }}</p>
    <p class="scrollbar-demo-item"><img alt="object" class="object" src="./assets/object.png"></p>
    <p class="scrollbar-demo-item"><img alt="vector" src="./assets/Vector 8.svg"></p>
    <p class="scrollbar-demo-item"><el-button type="primary">Upgrade Now</el-button></p>
  </el-scrollbar> -->

  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #F7F7F8;
}
body {
  margin: 0%;
}
.el-menu-vertical-demo {
  border-right: 0;
}
nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
