<template>
  <BaseList :headline="fruitsList.headline" :listItems="fruitsList.data">
    <template v-slot:header
      ><h3>Available {{ fruitsList.headline }}</h3></template
    >
    {{ fruitsList.introText }}
  </BaseList>

  <BaseList :headline="attendeesList.headline" :listItems="attendeesList.data">
    <template v-slot:header
      ><h3>{{ attendeesList.headline }} 2023</h3>
    </template>
    {{ attendeesList.introText }}
  </BaseList>

  <base-list :headline="fruitsList.headline" :listItems="fruitsList.data">
    <template v-slot:header>
      <h3>Früchte, die mit A anfangen</h3>
    </template>
    Alle Früchte, die mit dem Buchstaben <strong>A</strong> beginnen.
    <template v-slot:list-item="scopedData">
      <strong>Nr. {{ scopedData.item.id }}: </strong>{{ scopedData.item.text }}
      {{ scopedData.item.emoji }}
    </template>
  </base-list>

  <base-list headline="Früchte mit Emojis" :listItems="fruitsList.data">
    <template v-slot:list-item="scopedData">
      {{ scopedData.item.emoji }} {{ scopedData.item.text }}
    </template>
    Alle Früchte, die mit einem <strong>Emoji</strong> versehen sind.
  </base-list>

  <BaseList :headline="attendeesList.headline" :listItems="attendeesList.data">
    <template v-slot:header
      ><h3>{{ attendeesList.headline }} 2023</h3>
    </template>
    <h5>{{ attendeesList.introText }}</h5>
    <h5>All Bootcamp Attendees who began the Bootcamp in the year 2023</h5>
    <template v-slot:list-item="scopedData">
      {{ scopedData.item.text }} ({{ scopedData.item.age }})
    </template>
  </BaseList>

  <base-list :headline="flowersList.headline" :listItems="flowersList.data">
    <template v-slot:header>
      <h3>The most beautiful {{ flowersList.headline }} 💐</h3>
    </template>
    <h5>blooming now in Spring.</h5>
    <template v-slot:list-item="scopedData">
      Nr. {{ scopedData.item.id }}: <strong>{{ scopedData.item.text }}</strong>
      {{ scopedData.item.icon }}<br /><strong
        >€ {{ scopedData.item.price }}</strong
      >
    </template>
  </base-list>
</template>

<script>
import BaseList from "@/components/BaseList.vue";

export default {
  name: "App",
  components: {
    BaseList,
  },
  data() {
    return {
      fruitsList: {
        headline: "Fruits",
        introText: "A list of available fruits",
        data: [
          {
            id: 41,
            text: "Apple",
            emoji: "🍎 ",
          },
          {
            id: 22,
            text: "Melon",
            emoji: "🍉",
          },
        ],
      },
      attendeesList: {
        headline: "Bootcamp Attendees",
        introText: "A list of Bootcamp Attendees in 2023",
        data: [
          {
            id: 41,
            text: "Werner Hauff",
            age: "45",
          },
          {
            id: 22,
            text: "Melanie Halank",
            age: "37",
          },
        ],
      },
      flowersList: {
        headline: "Market Fresh Flowers",
        introText: "The most beautiful flowers blooming in Spring",
        data: [
          {
            id: 41,
            text: "Margarite",
            icon: "🌼 ",
            price: 1.35,
          },
          {
            id: 42,
            text: "Sun Flower",
            icon: "🌻 ",
            price: 2.45,
          },
          {
            id: 43,
            text: "Tulip",
            icon: "🌷 ",
            price: 1.75,
          },
          {
            id: 44,
            text: "Red Rose",
            icon: "🌹 ",
            price: 2.15,
          },
          {
            id: 45,
            text: "Fire Lily",
            icon: "🌸 ",
            price: 2.15,
          },
          {
            id: 46,
            text: "Hibiscus Flower",
            icon: "🌺 ",
            price: 2.35,
          },
        ],
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}
</style>
