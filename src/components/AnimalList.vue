<template>
  
  <ul>
    <li v-for="(animal, index) in animals" :key="index">
        {{ animal.type }}: 
        <span style="font-weight:bold;">{{ animal.name }}</span>, 
        <span style="font-style:italic;">{{ animal.date ? animal.date : 'undefined' }} </span>

        <button @click="removeAnimal">Remove animal</button>
    </li>
  </ul>

</template>

<script>
export default {
  data() {
    return {

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

  } //...methods
  
}
</script>

