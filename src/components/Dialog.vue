<template>
  <div class="about">
    <template>
      <v-row justify="center">
        <v-dialog
          v-model="dialog"
          persistent
          max-width="390"
          dark
          no-click-animation
          overlay-opacity="0.7"
        >
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              color="primary"
              v-bind="attrs"
              v-on="on"
              @click="preventEmptyFields()"
            >
              <slot />
            </v-btn>
          </template>
          <v-card>
            <v-toolbar dense class="d-inlin">
              <v-toolbar-title v-text="`title`" />

              <v-spacer></v-spacer>

              <v-btn icon @click="dialog = false">
                <v-icon>mdi-close</v-icon>
              </v-btn>
            </v-toolbar>

            <v-card-text class="mt-5">
              <v-select
                v-model="item1"
                :items="items"
                label="Somthing"
                outlined
                dense
                dark
              ></v-select>
              <v-select
                v-model="item2"
                :items="items2"
                label="Somthing"
                outlined
                dense
                dark
              ></v-select>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="red darken-2" text @click="dialog = false">
                Cancel
              </v-btn>
              <v-btn color="green darken-1" text @click="save()">
                Save
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-row>
    </template>
  </div>
</template>
<script>
export default {
  name: "Dialog",

  data() {
    return {
      items: ["A", "B", "C", "D"],

      items2: ["1", "2", "3", "4"],

      /* v-modeled to first List(items) */
      item1: "",
      /* v-modeled to Second List(items2) */
      item2: "",

      dialog: false
    };
  },
  methods: {
    save() {
      /* Provide Implementaion of Save Method */
      if (this.item1) {
        console.log(this.item1, this.item2);

        this.dialog = false;
      }
    },
    preventEmptyFields() {
      if (!(this.item1 && this.item2)) {
        this.item1 = this.items[0];
        this.item2 = this.items2[0];
      }
    }
  }
};
</script>
