<template>
  <div class="body">
    <navbar style="color: white; background: white;"/>
    <content-loader v-if="!myData" :height="1000" :width="400" :speed="1.5" primaryColor="#f0f0f0" secondaryColor="#dfdfdf">
    <rect x="10" y="99" rx="3" ry="3" width="380" height="6.4" />
    <rect x="11" y="117.22" rx="3" ry="3" width="249.24" height="7.94" />
    <rect x="9.5" y="12.27" rx="0" ry="0" width="379.2" height="77" />
    <rect x="216.5" y="209.21" rx="0" ry="0" width="170.66" height="30" />
    <rect x="10.5" y="156.27" rx="0" ry="0" width="197" height="86" />
    <rect x="218.5" y="157.27" rx="0" ry="0" width="161" height="7" />
    <rect x="218.5" y="172.69" rx="0" ry="0" width="128.8" height="5.6" />
    <rect x="219.5" y="188.25" rx="0" ry="0" width="138.46" height="6.02" />
    <circle cx="57.016648189186455" cy="180.78664818918645" r="7.516648189186454" />
    <rect x="209.5" y="268.27" rx="0" ry="0" width="181.24" height="86" />
    <rect x="11.5" y="273.27" rx="0" ry="0" width="161" height="7" />
    <rect x="11.5" y="290.69" rx="0" ry="0" width="128.8" height="5.6" />
    <rect x="10.5" y="309.25" rx="0" ry="0" width="138.46" height="6.02" />
    <rect x="9.5" y="324.27" rx="0" ry="0" width="170.66" height="30" />
    <rect x="9.5" y="373.27" rx="0" ry="0" width="379.2" height="77" />
    <rect x="9.5" y="461.27" rx="0" ry="0" width="379.2" height="77" />
    <rect x="9.5" y="552.27" rx="0" ry="0" width="182.016" height="77" />
    <rect x="204.5" y="551.27" rx="0" ry="0" width="182.016" height="77" />
    <rect x="7" y="641" rx="3" ry="3" width="380" height="6.4" />
    </content-loader>
    <main  v-else>
      <router-view/>
    </main>
  </div>
</template>

<script>

import { ContentLoader } from 'vue-content-loader'
import navbar from './components/navbar'

export default {
  components: {
    ContentLoader,
    navbar
  },
  data () {
    return {
      myData: null
    }
  },
  mounted () {
    // Just pretend this is an AJAX call. Use your imagination.
    setTimeout(() => {
      this.myData = 'Example Data'
    }, 3000)
  }
}
</script>

<style src="@/assets/styles/custom-css-library.css">
</style>
