<template>
  <h1>Vue version {{ version }}</h1>
  <div class="comments"><!--hello--></div>
  <pre>{{ time as string }}</pre>
  <div class="hmr-block">
    <Hmr />
  </div>
  <div class="hmr-tsx-block">
    <HmrTsx />
  </div>
  <TypeProps msg="msg" bar="bar" :id="123" />
  <Syntax />
  <PreProcessors />
  <CssModules />
  <Assets />
  <CustomBlock />
  <SrcImport />
  <Slotted>
    <div class="slotted">this should be red</div>
  </Slotted>
  <ScanDep />
  <TsImport />
  <Suspense>
    <AsyncComponent />
  </Suspense>
  <ReactivityTransform :foo="time" />
  <SetupImportTemplate />
  <WorkerTest />
  <Url />
</template>

<script setup lang="ts">
import { version } from 'vue'
import Hmr from './Hmr.vue'
import HmrTsx from './HmrTsx.vue'
import Syntax from './Syntax.vue'
import PreProcessors from './PreProcessors.vue'
import CssModules from './CssModules.vue'
import Assets from './Assets.vue'
import CustomBlock from './CustomBlock.vue'
import SrcImport from './src-import/SrcImport.vue'
import Slotted from './Slotted.vue'
import ScanDep from './ScanDep.vue'
import TsImport from './TsImport.vue'
import AsyncComponent from './AsyncComponent.vue'
import ReactivityTransform from './ReactivityTransform.vue'
import SetupImportTemplate from './setup-import-template/SetupImportTemplate.vue'
import WorkerTest from './worker.vue'
import { ref } from 'vue'
import Url from './Url.vue'
import TypeProps from './TypeProps.vue'

const time = ref('loading...')

window.addEventListener('load', () => {
  setTimeout(() => {
    const [entry] = performance.getEntriesByType('navigation')
    time.value = `loaded in ${entry.duration.toFixed(2)}ms.`
  }, 0)
})
</script>
