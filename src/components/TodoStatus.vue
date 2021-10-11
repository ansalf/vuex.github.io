<template>
  <div>
    <ul class="col justify-content-center px-2">
      <li>
        <button @click="changeTab" :class="{active:completed}" style="margin:3px 3px 3px 3px ;">Completed</button>
      </li>
      <li>
        <button @click="changeTab" :class="{active:!completed}" style="margin:3px 3px 3px 3px ;">Not Completed</button>
      </li>
    </ul>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  computed: {
    ...mapGetters(["completed"])
  },
  methods: {
    ...mapActions(["changeCompleted"]),
    changeTab() {
      this.changeCompleted();
    }
  }
};
</script>

<style scoped>
ul {
  list-style-type: none;
  display: flex;
}
button {
  outline: none;
  border: none;
  padding: 10px 20px;
  color: #000;
}
button:hover {
  outline: none;
  background-color: rgb(194, 243, 227);
}
.active {
  outline: none;
  color: white;
  background-color: rgb(0, 202, 135);
}
.active:hover {
  outline: none;
  border: none;
  padding: 10px 20px;
  color: white;
  background-color: rgb(0, 202, 135);
}
</style>