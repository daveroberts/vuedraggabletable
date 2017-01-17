<template>
  <div id="app">
    <table>
      <thead>
        <tr>
          <th>Table where sorting works.  No transition group</th>
        </tr>
      </thead>
      <draggable :list="people" :element="'tbody'">
        <tr v-for="person in people">
          <td>{{ person.name }}</td>
        </tr>
      </draggable>
      <tbody>
        <tr><td>Non-moving tbody goes here</td></tr>
      </tbody>
    </table>
    <table>
      <thead>
        <tr>
          <th>Table where sorting  does not work.  Has transition group</th>
        </tr>
      </thead>
      <draggable :list="places" :element="'tbody'">
        <transition-group>
          <tr v-for="country in places">
            <td>{{ country.name }}</td>
          </tr>
        </transition-group>
      </draggable>
      <tbody>
        <tr><td>Non-moving tbody goes here</td></tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import draggable from 'vuedraggable'
export default {
  name: 'app',
  data () {
    return {
      people: [
        {name: "Abby"},
        {name: "Brooke"},
        {name: "Courtenay"},
        {name: "David"}
      ],
      places: [
        {name: "Austria"},
        {name: "Bahamas"},
        {name: "Canada"},
        {name: "Djibouti"}
      ]
    }
  },
  components: { draggable }
}
</script>
<style>
table{ border: 1px solid black; margin: 2em; }
</style>
