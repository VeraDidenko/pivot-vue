<template>
  <div>
    <h3 class="page-title">Pivot Table Demo</h3>
    <Pivot
      ref="pivot"
      toolbar
      v-bind:height="600"
      v-bind:report="'https://cdn.flexmonster.com/github/demo-report.json'"
      v-bind:shareReportConnection="{url: 'https://olap.flexmonster.com:9500'}"
      v-bind:beforetoolbarcreated="customizeToolbar"
      _v-bind:licenseKey="'XXXX-XXXX-XXXX-XXXX-XXXX'"
    ></Pivot>
  </div>
</template>

<script lang="ts">
//Using the vue-flexmonster module (local registration):
//1. Importing the vue-flexmonster module:
import Pivot from "vue-flexmonster/vue3";
import * as Flexmonster from "flexmonster/types/flexmonster";
import { defineComponent } from 'vue';

export default defineComponent({
  name: "PivotTableDemo",
  methods: {
    customizeToolbar(toolbar: Flexmonster.Toolbar) : void {
      toolbar.showShareReportTab = true;
    }
  },
  //2. Defining the component:
  components: {
     Pivot
  }
});
</script>
