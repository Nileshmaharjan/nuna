<template>
  <div
    class="py-4 p-st"
    :class="{
      'bg-light': !nightMode,
      'bg-dark2': nightMode,
      'text-light': nightMode,
    }"
  >
    <div class="container">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >Highlights</span
        >
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <div class="row">
        <div class="col-xl-12 col-bg-12 col-md-12 col-sm-12">
          <HighlightHelper :data="highlight" :nightMode="nightMode" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HighlightHelper from "./helpers/HighlightHelper";
import info from "../../info";

export default {
  name: "Highlights",
  components: {
    HighlightHelper,
  },
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      highlight: {
        data: info.highlights,
      },
    };
  },
};
</script>

<style scoped>
.title {
  font-size: 30px;
  font-weight: 500;
}
</style>
