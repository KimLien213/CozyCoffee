<template>
   <v-card
    :color="active ? '#F6EFEF' : 'white'"
    :class="active ? 'borderme' : 'borderout'"
    class="d-flex align-center rounded-lg mx-2"
    dark
    height="140"
    @click="eventClick"
    flat
  >
    <v-row>
      <v-col cols="12" sm="12">
        <v-list-item three-line class="text-center">
          <v-list-item-content>
            <div align="center" justify="center">
              <v-img
                :src="imageURL"
                max-height="100"
                max-width="100"
                contain
              ></v-img>
            </div>
            <v-list-item-subtitle
              :class="active ? 'brown--text' : 'black--text'"
              class="caption mt-4"
            >
              {{ name }}
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>

export default {
  props: {
    active: Boolean,
    name: String,
    imageURL: String,
    eventClick: Function
  }, 
  methods: {
    // TODO
  }
};
</script>
<style>
.v-card.borderme {
  border: 2px solid #3a6d5b !important;
}
.v-card.borderout {
  border: 1px solid #bcaaa4 !important;
}
#app {
  background-image: url('~@/assets/bg.jpg');
  background-repeat: repeat;
}
</style>
