<template>
  <header>
    <div class="d-flex justify-content-center align-items-center my-4">
      <span class="header-tab px-2">Colors </span>
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right"
        viewBox="0 0 16 16">
        <path fill-rule="evenodd"
          d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708" />
      </svg>

      <span class="header-tab px-2">Colors Palettes </span>
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right"
        viewBox="0 0 16 16">
        <path fill-rule="evenodd"
          d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708" />
      </svg>

      <span class="header-combination-title px-2"> {{ combinationName }}</span>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderLayout",
  props: {
    combinationName: {
      type: String,
      required: true
    }
  }
}
</script>