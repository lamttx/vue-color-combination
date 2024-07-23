<template>
  <div class="text-center">
    <h2 class="combination-related-title mb-5">Related Combinations</h2>
    <div class="combination-related row justify-content-between">
      <div v-for="(comb, index) in relatedCombinations" :key="index"
        class="d-flex justify-content-center align-items-center col-6 my-3">
        <div v-for="color in comb.colors" :key="color">
          <div :style="{ backgroundColor: color }" class="combination-related-color-item-square"></div>
        </div>
      </div>
    </div>
    <div class="combination-browse-template-title">
      <h3>Use this color palette and create beautiful <br /> designs and documents!</h3>
      <button role="button" class="border-0 rounded py-2 px-3 mt-3" :style="{ backgroundColor: '#F7CAC9' }">Browse
        templates</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RelatedCombination',
  props: {
    relatedCombinations: {
      type: Array,
      required: true
    }
  },
}
</script>