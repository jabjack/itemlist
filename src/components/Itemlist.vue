<template>

  <div class="m-auto space-y-6 > * + *" >



    <h1 class=" font-serif text-2xl text-center mt-12 cursor-none truncate"> Fruit List  {{ herosCount }}</h1>

    <ul>
      <li
        class="flex justify-between   mt-6 cursor-none"
        v-for="(hero, index) in dcHeros"
        :key="hero.name"

      >
        <div>
          {{ hero.name }}
        </div>

        <button class="mx-20 opacity-3 bg-blend-normal" v-on:click="remove(index)"> x </button>

      </li>
 

    <form class="mt-10" @submit.prevent = "addHero">

      <input v-model="newHero" class="border rounded space-x-1.5 > * + *  justify-between shadow-md " placeholder="Type the new Item" />

      <button type="submit" class=" py-0 px-2 my-0 mx-50px bg-emerald-500 shadow-md   border rounded  mx-8 space-x-20 font-serif font-black tracking-tighter decoration-solid  text-white" > Add Item </button>


    </form>

  </ul>

  </div>

</template>

<script>

export default {

    // eslint-disable-next-line vue/multi-word-component-names
    name: "Itemlist",

  data() {

    return {
      newHero: "",

      dcHeros: [
        { name: "Coco" },
        { name: "pineapple" },
        { name: "apple" },
        { name: "orange" },
        { name: "lemon" },
        { name: "strawberry" },
      ],
    };
  },

  computed: {

    herosCount() {
      return this.dcHeros.length;
    },
  },

  methods: {

    addHero() {

      if (this.newHero != "") {

        this.dcHeros.push({ name: this.newHero });

        this.newHero = "";
      }
    },

    remove(index) {

      this.dcHeros = this.dcHeros.filter((hero, i) => i != index);
      
    },

  },

};
</script>

<style>
</style>