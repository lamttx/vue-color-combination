<template>
    <div class="container">
        <div class="w-75 mx-auto">
            <HeaderLayout :combinationName="currentCombination.name" />
            <ColorCombination :combination="currentCombination" />
            <RelatedCombination @change-combination="handleUpdateCombination" :relatedCombinations="currentRelated" />
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
        const defaultCombination = combinations[0].combination;
        const defaultRelated = combinations[0].relatedCombinations;
        let currentCombination = ref(defaultCombination);
        let currentRelated = ref(defaultRelated);
        let checkNewCombination = undefined;

        const handleUpdateCombination = (id) => {
            if (id) {
                let newCombination = combinations.find((x) => x.combination.id === id);
                checkNewCombination = newCombination;
            }
            currentCombination.value = checkNewCombination ? checkNewCombination.combination : defaultCombination;
            currentRelated.value = checkNewCombination ? checkNewCombination.relatedCombinations : defaultRelated;

            document.body.style.backgroundColor = (currentCombination.value).color.hex;
        };
        return { handleUpdateCombination, currentCombination, currentRelated };
    },
}
</script>