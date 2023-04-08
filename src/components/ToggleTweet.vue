<script setup>
import { ref, defineProps } from "vue";
import TwitterCardVue from "./TwitterCard.vue";

const showImage = ref(true);

const props = defineProps({
  btnDescription: {
    type: String,
    default: "Ver tweet",
  },
});
</script>

<template>
  <div>
    <v-row>
      <v-col align="center" class="ma-6">
        <v-btn
          id="toogle"
          variant="outlined"
          width="15rem"
          height="2.8rem"
          @click="showImage = !showImage"
        >
          {{ btnDescription }}
        </v-btn>
      </v-col>
    </v-row>

    <v-row>
      <v-slide-y-transition>
        <TwitterCardVue v-if="showImage" />
      </v-slide-y-transition>
    </v-row>
  </div>
</template>

<style scoped>
#toogle {
  padding: 15px;
  background-color: rgb(29, 155, 240);
  color: #fff;
  border-radius: 30px;
}
</style>
