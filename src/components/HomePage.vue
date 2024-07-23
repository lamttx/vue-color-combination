<template>
    <div class="container">
        <div class="w-75 mx-auto">
            <HeaderLayout :combinationName="currentCombination.name" />
            <ColorCombination :combination="currentCombination" />
            <RelatedCombination :relatedCombinations="currentRelated" />
        </div>
    </div>
</template>

<script>
import { ref } from "vue";
import HeaderLayout from '@/layout/HeaderLayout.vue';
import ColorCombination from './ColorCombination.vue';
import RelatedCombination from './RelatedCombination.vue'
import { combinations } from "@/assets/jsons/combinations/combinations.json";

export default {
    name: 'HomePage',
    components: {
        HeaderLayout,
        ColorCombination,
        RelatedCombination
    },
    setup() {
        const currentCombination = ref(combinations[0].combination);
        const currentRelated = ref(combinations[0].relatedCombinations);
        return { currentCombination, currentRelated };
    },
}
</script>