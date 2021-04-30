<template>
  <div>
    <!-- When calling this componenet these values must be binded to it.
       "value"         "Description"
    title            
    list1             items of first list
    list2             items of second list
    subTitle1         Title of the first list(v-select) 
    subTitle2         Title of the second list(v-select) 
     -->
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
            <v-btn color="primary" v-bind="attrs" v-on="on">
              <!-- This slot is used for providing activating text of this Dialog -->
              <slot />
            </v-btn>
          </template>
          <v-card>
            <v-toolbar dense class="d-inlin">
              <v-toolbar-title v-text="title" />

              <v-spacer></v-spacer>

              <v-btn icon @click="dialog = false">
                <v-icon>mdi-close</v-icon>
              </v-btn>
            </v-toolbar>

            <v-card-text class="mt-5">
              <v-select
                v-model="item1"
                :items="list1"
                :label="subTitle2"
                outlined
                dense
                dark
              ></v-select>
              <v-select
                v-model="item2"
                :items="list2"
                :label="subTitle1"
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
  name: "baseDialog",
  props: {
    list1: {
      type: Array,
      default() {
        return ["addListAsProps(list1)"];
      }
    },
    list2: {
      type: Array,
      default() {
        return ["addListAsProps(list2)"];
      }
    },
    title: {
      type: String,
      default: "addTitleAsProps(title)"
    },
    subTitle1: {
      type: String,
      default: "addSubTitleAsProps(subTitle1)"
    },
    subTitle2: {
      type: String,
      default: "addSubTitleAsProps(subTitle2)"
    }
  },
  data() {
    return {
      /* v-modeled to first List(v-select) */
      item1: this.list1[0],
      /* v-modeled to Second List(v-select) */
      item2: this.list2[0],

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
    }
  }
};
</script>
