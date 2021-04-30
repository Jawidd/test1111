<template>
  <div class="about">
    <base-dialog> asdf</base-dialog>
    <!--  -->

    <props-dialog
      class="my-10"
      title="asdf"
      :list1="items"
      :list2="items2"
      subTitle1="Category"
      subTitle2="item"
      >props Dialog</props-dialog
    >

    <!--  -->
    <!--  -->
    <!--  -->
    <v-btn color="green" dense class="my-15">Click</v-btn>
    <template class=" blue--text">
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
            <v-btn color="green" dark v-bind="attrs" v-on="on">
              Open Dialog
            </v-btn>
          </template>
          <v-card>
            <v-toolbar dense class="d-inlin">
              <v-toolbar-title>Title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon @click="dialog = false">
                <v-icon>mdi-close</v-icon>
              </v-btn>
            </v-toolbar>

            <v-card-text class="mt-5">
              <v-select
                :items="items"
                label="Somthing"
                outlined
                dense
                dark
              ></v-select>
              <v-select
                :items="items"
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
              <v-btn color="green darken-1" text @click="dialog = false">
                OK
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-row>
    </template>
  </div>
</template>
<script>
//import dialog from "@/components/Dialog";
import baseDialog from "../components/Dialog.vue";
import propsDialog from "../components/propsDialog.vue";
export default {
  data() {
    return {
      dialog: false,
      items: ["Foo", "Bar", "Fizz", "Buzz"],
      items2: ["One", "Two", "Three", "Four"],
      result: []
    };
  },
  components: {
    baseDialog,
    propsDialog
  },
  methods: {}
};
</script>
