<script setup>
import CodeEditor from '~/components/CodeEditor.vue'
import Fold from '~/components/Fold.vue'
import FoldH2 from '~/components/FoldH2.vue'
import ExOptionsData from '~/contents/data-refs/counter-examples/ExOptionsData.vue'
import examples from '~/data/examples-props-refs.js'
import ExApiRef from '~/contents/data-refs/counter-examples/ExApiRef.vue'
</script>

<template>
  <div class="props-refs page">
    <h1>data / refs</h1>
    <FoldH2 :defaultOpen="true">
      <template #title>Options API: Define Reactive Stuff</template>
      <template #content>
        <CodeEditor :content="examples.optionsData" />
        <Fold>
          <template #title>Show Example</template>
          <template #content>
            <ExOptionsData />
          </template>
        </Fold>
      </template>
    </FoldH2>

    <FoldH2 :defaultOpen="true">
      <template #title>
        Composition API: Define Reactive Stuff with <code>ref</code>
      </template>
      <template #content>
        <CodeEditor :content="examples.compositionRef" />
        <Fold>
          <template #title>Show Example</template>
          <template #content>
            <ExApiRef />
          </template>
        </Fold>
      </template>
    </FoldH2>
  </div>
</template>

<style scoped>
.page.props-refs {
  padding-top: 50px;
  padding-bottom: 50px;
}
</style>
