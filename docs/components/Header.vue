<template>
  <v-toolbar-title v-cloak style="min-height: 104px;">
    <v-container class="summary">
      <v-row style="height:100%;" no-gutters>

        <v-col cols="12" sm="9">
          <h3>{{title}}</h3>
          <p id="author-name" v-html="author"></p>
        </v-col>

        <v-col class="align-end" cols="12" sm="3" style="text-align: right;">
        </v-col>

      </v-row>
      <v-row><v-progress-linear v-model="progress" id="prog" height="7"></v-progress-linear></v-row>
    </v-container>
  </v-toolbar-title>
</template>

<script>
  module.exports = {
    props: {
      essayConfig: Object,
      siteConfig: Object,
      progress: Number
    },    
    data: () => ({}),
    computed: {
      title() { return  this.essayConfig.title || this.siteConfig.title },
      author() { return this.essayConfig.author || '&nbsp;' },
      numMaps() { return this.essayConfig['num-maps'] }
    }
  }
</script>

<style>
  [v-cloak] { display: none; }

  header {
    font-size: 0.8rem !important;
  }
  .summary {
    line-height: 1.1rem;
  }
  .summary h3 {
    font-size: 2.0rem !important;
    margin: 32px 0 0 0 ! important;
    padding-left: 0;
  }
  #author-name {
    font-size: 1.0rem;
    margin: 6px 0;
  }
</style>