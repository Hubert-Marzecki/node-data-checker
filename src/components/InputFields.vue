<template>
  <div class="container mx-auto ">
    <h1 class="section__header mt-10 mb-4">INSERT TEXT TO CHECK ON WEBISTE</h1>

  <div class=" mb-10">
  <div v-for="(item, index) in copys" :key="item.index" class="flex flex-col">
    <label for="fname">Insert copy:  </label>
    <input type="text"  name="fname" class="py-2 px-4 rounded bg-blue-200 input-field" @change="(e) => updateValue(index, e.target.value)" />
  </div>
  </div>

 <button 
    @click="addField" 
    class="add__field__button bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
    id="add__coppys__field"
    >
    ADD ANOTHER COPY FIELD
    </button>
  </div>
</template>

<script>
import { bus } from '../main';
export default {
  name: "InputFields",
  data() {
    return {
      copys: [""],
    };
  },
  methods: {
    addField(e)  {
        this.copys.push(e.target.value)
    },
    updateValue(x,e) {
      this.copys[x] = e;
  }
  }
};
</script>

<style>

.section__header{
  font-size: 1.6em;
  font-weight: 700;
}
.input-field{
  background-color:lightblue;
}

</style>
