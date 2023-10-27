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
              <el-tag class="message-count ml-2" type="danger">49</el-tag>
            </el-menu-item>
            <el-menu-item index="7">
              <el-icon><img src="./assets/notification.svg"></el-icon>
              <span>Notification</span>
            </el-menu-item>
            <el-menu-item index="8">
              <el-icon><img src="./assets/settings.svg"></el-icon>
              <span>Settings</span>
            </el-menu-item>
            <p class="illustration"><img alt="object" class="object" src="./assets/object.png"></p>
            <p class="illustration"><img alt="vector" src="./assets/Vector 8.svg"></p>
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
          <el-table-column prop="gender" label="Gender" >
            <template #default="scope">
              <el-tag 
              class="mx-1" 
              effect="light" 
              round
              :type="scope.row.gender === 'Male' ? '' : 'warning'"
              >{{ scope.row.gender }}</el-tag>
            </template>
          </el-table-column>
          <el-table-column fixed="right" width="120">
            <template #default>
              <el-dropdown>
                <span class="el-dropdown-link">
                  ...
                </span>
                <template #dropdown>
                  <el-dropdown-menu>
                    <el-dropdown-item>
                      <el-button size="small" type="primary" plain @click="toggle(true)">Edit</el-button>
                    </el-dropdown-item>
                    <el-dropdown-item><el-button size="small" type="danger" plain>Delete</el-button></el-dropdown-item>
                  </el-dropdown-menu>
                </template>
              </el-dropdown>
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

    <el-dialog v-model="dialogFormVisible2" title="Edit Customer">
      <el-form>
        <el-form-item>
          <el-input autocomplete="off" placeholder="John Deo"/>
        </el-form-item>

      </el-form>
      <template #footer>
                          <span class="dialog-footer">
                            <el-button @click="toggle(false)">Close</el-button>
                            <el-button type="primary" @click="toggle(false)">
                              Save
                            </el-button>
                          </span>
      </template>
    </el-dialog>

  </el-container>

  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/> -->
</template>

<script setup>
import { reactive, ref } from 'vue'

const dialogFormVisible = ref(false)
const dialogFormVisible2 = ref(false)
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

const toggle = (status) => {
  dialogFormVisible2.value = status
}

const tableData = [
  {
    name: 'John Deo',
    email: 'johndoe2211@gmail.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'Shelby Goode',
    email: 'shelbygoode481@gmail.com',
    phonenumber: '+33757005467',
    gender: 'Female'
  },
  {
    name: 'Robert Bacins',
    email: 'robertbacins4182@.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'John Carilo',
    email: 'john carilo182@.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'Adriene Watson',
    email: 'adrienewatson82@.com',
    phonenumber: '+83757305467',
    gender: 'Female'
  },
  {
    name: 'Jhon Deo',
    email: 'jhondeo24823@.com',
    phonenumber: '+63475700546',
    gender: 'Male'
  },
  {
    name: 'Mark Ruffalo',
    email: 'markruffalo3735@.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'Bethany Jackson',
    email: 'bethanyjackson5@.com',
    phonenumber: '+33757005467',
    gender: 'Female'
  },
  {
    name: 'Christine Huston',
    email: 'christinehuston4@.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'Anne Jacob',
    email: 'annejacob2@ummoh.com',
    phonenumber: '+33757005467',
    gender: 'Male'
  },
  {
    name: 'James Mullican',
    email: 'jamesmullican5346@.com',
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

.illustration {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  margin: 10px;
  text-align: center;
  border-radius: 4px;
}

.message-count {
  margin-left: 37px;
}

.example-showcase .el-dropdown-link {
  display: flex;
  align-items: center;
}
</style>
