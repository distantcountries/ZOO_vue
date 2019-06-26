<template>
  
  <ul>
    <li v-for="(animal, index) in animals" :key="index">
        <span style="font-weight:bold;">{{ animal.type }}:</span> {{ animal.name }} {{ animal.date }}
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
  } //...data
  
}
</script>

