<template>
  <div class="text-center">
    <h2 class="combination-related-title mb-5">Related Combinations</h2>
    <div class="combination-related row justify-content-between">
      <div v-for="(comb, index) in relatedCombinations" :key="index" role="button"
        class="d-flex justify-content-center align-items-center col-6 my-3" @click="changeColorCombination(comb.id)">
        <div v-for="(color, indexColor) in comb.colors" :key="indexColor">
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
import ColorCombination from './ColorCombination.vue';

export default {
  name: 'RelatedCombination',
  components: {
    ColorCombination
  },
  props: {
    relatedCombinations: {
      type: Array,
      required: true
    }
  },
  methods: {
    changeColorCombination(combinationId) {
      this.$emit('change-combination', combinationId);
    }
  }
}
</script>