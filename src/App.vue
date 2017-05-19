<template>
  <div id="app">
    <link rel="stylesheet" href="//fonts.googleapis.com/css?family=Roboto:300,400,500,700,400italic">
    <link rel="stylesheet" href="//fonts.googleapis.com/icon?family=Material+Icons">
    
    <template>
      <md-toolbar>
        <h1 class="md-title" style="flex: 1">The Top</h1>
        <md-input-container md-inline v-if="shouldShowSearch">
          <label>Inline field</label>
          <md-input v-model="searchTerm"></md-input>
          <md-icon v-on:click.native="hideSearch">cancel</md-icon>
        </md-input-container>
         <md-button v-else class="md-icon=button">
           <md-icon v-on:click.native="showSearch">search</md-icon>
         </md-button>
      </md-toolbar>
      <div id="main-content">
        <router-view></router-view>
      </div>
      <md-toolbar><h1 class="md-title">The Bottom</h1></md-toolbar>
    </template>
  </div>
</template>

<style scoped>
  #main-content {
    padding: 20px;
  }
</style>

<script>
import 'vue-material/dist/vue-material.css'

export default {
  methods: {
    hideSearch () {
      this.searchTerm = null
      this.shouldShowSearch = false
    },
    showSearch () {
      this.shouldShowSearch = true
    }
  },
  data () {
    return {
      shouldShowSearch: false,
      searchTerm: null
    }
  }
}
</script>
