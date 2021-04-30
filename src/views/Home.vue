<template>
  <div class="Home">
    <props-dialog
      class="my-10 mx-4 d-inline-block"
      title="asdf"
      :list1="items"
      :list2="items2"
      subTitle1="Category"
      subTitle2="item"
      >props Dialog</props-dialog
    ><a
      href="https://github.com/Jawidd/test1111/blob/master/src/components/propsDialog.vue"
      >Code link</a
    >
    <br />
    <base-dialog class="my-10 mx-4 d-inline-block"> Dialog</base-dialog>
    <a
      href="https://github.com/Jawidd/test1111/blob/master/src/components/Dialog.vue"
      >Code link</a
    >
  </div>
</template>
<script>
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
