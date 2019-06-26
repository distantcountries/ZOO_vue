<template>
  <div>

  <form @submit.prevent="addAnimal">

    <div style="margin:0.5rem;">
      <label for="type">Type</label>
      <input id="type" type="text" v-model="animal.type">
    </div>

    <div style="margin:0.5rem;">
      <label for="name">Name</label>
      <input id="name" type="text" v-model="animal.name">
    </div>

    <div style="margin:0.5rem;">
      <label for="date">Date</label>
      <input id="date" type="text" v-model="animal.date">
    </div>

    <div style="margin:0.5rem;">
      <button >Add animal</button>
    </div>

  </form>


  <ul>
    <li v-for="(animal, index) in animals" :key="index"
          style="margin:0.5rem;">
      <button @click="moveToTop(index)">Move to top</button>

        {{ animal.type }}: 
        <span style="font-weight:bold;">{{ animal.name }}</span>, 
        <span style="font-style:italic;">{{ animal.date ? animal.date : 'undefined' }} </span>

        <button @click="removeAnimal(index)">Remove animal</button>
    </li>
  </ul>

  </div>
</template>

<script>
export default {
  data() {
    return {

      animal: {
        type: '', 
        name: '', 
        date: ''
      },

      animals: [
        { type: 'Parrot', name: 'Pera', date: '17.02.2019' },
        { type: 'Dog', name: 'Boba', date: '11.07.2013' },
        { type: 'Cat', name: 'Kitty', date: '' },
        { type: 'Horse', name: 'Kan', date: '' },
        { type: 'Sheep', name: 'Shone', date: '21.11.2016' }
      ],

    } //...return
  }, //...data

  methods: {

    removeAnimal(index) {
      this.animals.splice(index, 1)
    }, //...removeAnimal

    moveToTop(index) {
      let animalCopy = this.animals[index];
      this.animals.splice(index, 1);
      this.animals.unshift(animalCopy);
    },

    addAnimal() {
      this.animals.push(this.animal);

      this.animal = {
        type: '', 
        name: '', 
        date: ''
      };
    }, //...addAnimal





  } //...methods
  
}
</script>

