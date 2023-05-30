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

  <base-list headline="Früchte, die mit A anfangen" :listItems="fruitsList.data"
    >Alle Früchte, die mit dem Buchstaben <strong>A</strong> beginnen.
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
