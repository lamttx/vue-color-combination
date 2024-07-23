<template>
    <div class="mb-5 pb-5 text-center">
        <h1 class="combination-title">{{ combination.name }} <br /> color combination</h1>
        <div>
            <div class="combination-featured-image position-relative">
                <img :src="`${featuredImageUrl}${combination.featuredImage.url}`" :alt="combination.color.name" />
                <button role="button" class="combination-button-likes border-0 rounded px-3 py-2 position-absolute">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currenColor"
                        class="bi bi-heart me-1" viewBox="0 0 16 16">
                        <path
                            d="m8 2.748-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385.92 1.815 2.834 3.989 6.286 6.357 3.452-2.368 5.365-4.542 6.286-6.357.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143q.09.083.176.171a3 3 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15" />
                    </svg>
                    {{ combination.likes }}
                </button>
            </div>
            <div class="row">
                <div v-for="color in combination.colors" :key="color.hex" class="col-3 px-0">
                    <div :style="{ backgroundColor: color.hex }" class="combination-color-item-square">
                        <div
                            class="combination-color-item-square-hover d-flex justify-content-center align-items-center">
                            <p class="mb-0">Copy</p>
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                class="bi bi-check-lg combination-color-item-square-checked-icon" viewBox="0 0 16 16">
                                <path
                                    d="M12.736 3.97a.733.733 0 0 1 1.047 0c.286.289.29.756.01 1.05L7.88 12.01a.733.733 0 0 1-1.065.02L3.217 8.384a.757.757 0 0 1 0-1.06.733.733 0 0 1 1.047 0l3.052 3.093 5.4-6.425z" />
                            </svg>
                        </div>
                    </div>
                    <p class="combination-color-item-name mt-4 mb-0">{{ color.name }}</p>
                    <p class="combination-color-item-hex-code">{{ color.hex }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'ColorCombination',
    props: {
        combination: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            featuredImageUrl: '/images/Thumbnail/'
        }
    },
}
</script>