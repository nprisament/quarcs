<template>
  <a :href="advertisement.url" rel="noopener" target="_blank">
    <div
      class="sponsor-img"
      :style="'background:' + advertisement.backgroundColor"
    >
      <img
        :src="baseUrl + advertisement.desktop_path"
        :alt="advertisement.altText"
        class="d-none d-lg-inline-block d-xl-inline-block"
      />
      <img
        v-if="hasTablet"
        :src="baseUrl + advertisement.tablet_path"
        :alt="advertisement.altText"
        class="d-none d-sm-inline-block d-md-inline-block d-lg-none"
      />
      <img
        :src="baseUrl + advertisement.mobile_path"
        :alt="advertisement.altText"
        :class="
          'd-inline-block d-lg-none d-xl-none ' +
          (hasTablet ? 'd-sm-none d-md-none' : '')
        "
      />
    </div>
  </a>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import { shortSemToURL } from "@/utilities";
import { Advert } from "@/typings";

@Component
export default class AdvertImage extends Vue {
  @Prop() readonly advertisement!: Advert;

  baseUrl = `${shortSemToURL()(process.env.VUE_APP_CURR_SEM)}/img`;

  get hasTablet(): boolean {
    return this.advertisement.tablet_path !== undefined;
  }
}
</script>

<style scoped>
.sponsor {
  margin-bottom: 1rem;
}

.sponsor > a > span {
  color: var(--raw-link);
}

.sponsor-img {
  text-align: center;
}
</style>
