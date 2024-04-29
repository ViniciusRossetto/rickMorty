<script setup>
import {ref} from "vue"

let num = ref(0)
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark border-bottom border-body">
    <div class="container-fluid">
      <div class="collapse navbar-collapse" id="navbarNav">
        <div id="button-nav">
          <router-link id="home" class="nav-link" aria-current="page" to="/">Home</router-link>
        </div> 
      </div>  
      <router-link class="navbar-brand" to="/">R&M API</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbar" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <div id="button-nav">
          <router-link class="nav-link" aria-current="page" to="/about">About</router-link>
        </div>
      </div>
    </div>
  </nav>

  <div class="main">
      <router-view></router-view>
  </div>

  <footer class="bg-dark text-light">
    <div>
      Unimar | ADS | {{ new Date().getFullYear() }}
    </div>
  </footer>
</template>

<style>
.nav-link{
  color: white;
}

#navbarNav{
  width: 30px; 
}

#home{
  padding-left: 640px
}

  footer{
    position: fixed;
    bottom: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
  }
</style>