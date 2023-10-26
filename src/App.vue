<template>
  <el-container class="layout-container">
    <el-aside width="218px">
      <el-container class="sidebar">
        <el-header>
          <el-row>
            <img src="./assets/logo.svg">
            <h2>Base</h2>
          </el-row>
        </el-header>
      
        <el-main class="sidebar-menu">
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
              <el-tag class="ml-2" type="danger">49</el-tag>
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
        </el-main>
      </el-container>
    </el-aside>

    <el-container class="main">
      <el-header>
        <el-row class="row-bg" justify="space-between">
          <el-col :span="6">Customer List</el-col>
          <el-col :span="6">
            <el-button type="primary" @click="dialogFormVisible = true">Add Customer</el-button>
            <el-dialog v-model="dialogFormVisible" title="Add Customer">
              <el-form :model="form">
                <el-form-item>
                  <el-input v-model="form.name" autocomplete="off" placeholder="Add name"/>
                </el-form-item>
                
              </el-form>
              <template #footer>
                <span class="dialog-footer">
                  <el-button @click="dialogFormVisible = false">Close</el-button>
                  <el-button type="primary" @click="dialogFormVisible = false">
                    Add People
                  </el-button>
                </span>
              </template>
            </el-dialog>
          </el-col>
        </el-row>
      </el-header>
      <el-main>  
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="name" label="Name" width="180" />
          <el-table-column prop="email" label="Email" />
          <el-table-column prop="phonenumber" label="Phone number" />
          <el-table-column prop="gender" label="Gender" />
          <el-table-column fixed="right" width="120">
            <template #default>
              <el-button link type="primary" size="small">Detail</el-button>
              <el-button link type="primary" size="small">Edit</el-button>
            </template>
          </el-table-column>
        </el-table>
    </el-main>
    </el-container>

    <el-aside class="profile" width="302px">
      <h1>John Deo</h1>
      <h3>UI/UX Designer</h3>
      <hr>
      <h2>Contact Info </h2>
      <el-progress type="circle" :percentage="70" />
      <el-progress type="circle" :percentage="60" />
    </el-aside>
  </el-container>

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

<script setup>
import { reactive, ref } from 'vue'

const dialogTableVisible = ref(false)
const dialogFormVisible = ref(false)
const formLabelWidth = '140px'

const form = reactive({
  name: '',
  region: '',
  date1: '',
  date2: '',
  delivery: false,
  type: [],
  resource: '',
  desc: '',
})

const tableData = [
  {
    name: 'John Deo',
    email: 'johndoe2211@gmail.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'John Deo',
    email: 'johndoe2211@gmail.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
]
</script>

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

.sidebar {
  background-color: #fff;
}

.sidebar-menu {
  padding: 0;
}

.profile {
  background-color: #fff;
}

table {
  border-collapse: separate; 
  border-spacing: 0 10px;
  background-color: #F7F7F8;
}
</style>
