<template>
  <article>
    <h1>Noten</h1>
    <p>Just a table for myself that represents the grading system that is relevant to me.</p>

    <label>
      Enter the maximum number of points in the text field to see the points for each grade:
      <input type="number" v-model.number="max"/>
    </label>

    <h2>Gymnasium</h2>
    <table>
      <thead>
      <tr>
        <th>Punkte</th>
        <th>Notewort</th>
        <th>Note</th>
        <th>BE</th>
        <th>Rohpunkte</th>
        <th>Notendefinition</th>
        <th>Bemerkung</th>
      </tr>
      </thead>
      <tbody>
      <tr class="green1">
        <td>15</td>
        <td rowspan="3">sehr gut</td>
        <td>1+</td>
        <td>{{ calc(max, 95) }}</td>
        <td>95 %</td>
        <td rowspan="3">
          <i>
            Die Leistungen entsprechen den Anforderungen in besonderem Maße.
          </i>
        </td>
        <td rowspan="3"></td>
      </tr>
      <tr class="green1">
        <td>14</td>
        <td>1</td>
        <td>{{ calc(max, 90) }}</td>
        <td>90 %</td>
      </tr>
      <tr class="green1">
        <td>13</td>
        <td>1−</td>
        <td>{{ calc(max, 85) }}</td>
        <td>85 %</td>
      </tr>
      <tr class="green2">
        <td>12</td>
        <td rowspan="3">gut</td>
        <td>2+</td>
        <td>{{ calc(max, 80) }}</td>
        <td>80 %</td>
        <td rowspan="3">
          <i>Die Leistungen entsprechen den Anforderungen voll.</i>
        </td>
        <td rowspan="3"></td>
      </tr>
      <tr class="green2">
        <td>11</td>
        <td>2</td>
        <td>{{ calc(max, 75) }}</td>
        <td>75 %</td>
      </tr>
      <tr class="green2">
        <td>10</td>
        <td>2−</td>
        <td>{{ calc(max, 70) }}</td>
        <td>70 %</td>
      </tr>
      <tr class="yellow1">
        <td>9</td>
        <td rowspan="3">befriedigend</td>
        <td>3+</td>
        <td>{{ calc(max, 65) }}</td>
        <td>65 %</td>
        <td rowspan="3">
          <i>Die Leistungen entsprechen den Anforderungen im Allgemeinen.</i>
        </td>
        <td rowspan="3"></td>
      </tr>
      <tr class="yellow1">
        <td>8</td>
        <td>3</td>
        <td>{{ calc(max, 60) }}</td>
        <td>60 %</td>
      </tr>
      <tr class="yellow1">
        <td>7</td>
        <td>3−</td>
        <td>{{ calc(max, 55) }}</td>
        <td>55 %</td>
      </tr>
      <tr class="yellow2">
        <td>6</td>
        <td rowspan="2">ausreichend</td>
        <td>4+</td>
        <td>{{ calc(max, 50) }}</td>
        <td>50 %</td>
        <td rowspan="2">
          <i>
            Die Leistungen weisen zwar Mängel auf, entsprechen aber im Ganzen noch den Anforderungen.
          </i>
        </td>
        <td rowspan="2"></td>
      </tr>
      <tr class="yellow2">
        <td>5</td>
        <td>4</td>
        <td>{{ calc(max, 45) }}</td>
        <td>45 %</td>
      </tr>
      <tr class="orange">
        <td>4</td>
        <td><i>schwach</i> ausreichend</td>
        <td>4−</td>
        <td>{{ calc(max, 39) }}</td>
        <td>39 %</td>
        <td>
          <i>
            Die Leistungen weisen Mängel auf und entsprechen den Anforderungen nur noch mit Einschränkungen.
          </i>
        </td>
        <td rowspan="4"><i>defizitärer Bereich</i></td>
      </tr>
      <tr class="orange">
        <td>3</td>
        <td rowspan="3">mangelhaft</td>
        <td>5+</td>
        <td>{{ calc(max, 33) }}</td>
        <td>33 %</td>
        <td rowspan="3">
          <i>
            Die Leistungen entsprechen den Anforderungen nicht, lassen jedoch
            erkennen, dass die notwendigen Grundkenntnisse vorhanden sind und
            die Mängel in absehbarer Zeit behoben werden können.
          </i>
        </td>
      </tr>
      <tr class="orange">
        <td>2</td>
        <td>5</td>
        <td>{{ calc(max, 27) }}</td>
        <td>27 %</td>
      </tr>
      <tr class="orange">
        <td>1</td>
        <td>5−</td>
        <td>{{ calc(max, 20) }}</td>
        <td>20 %</td>
      </tr>
      <tr class="red">
        <td>0</td>
        <td>ungenügend</td>
        <td>6</td>
        <td>0</td>
        <td>0 %</td>
        <td>
          <i>
            Die Leistungen entsprechen den Anforderungen nicht und selbst die
            Grundkenntnisse sind so lückenhaft, dass die Mängel in absehbarer
            Zeit nicht behoben werden können.
          </i>
        </td>
        <td><i>nicht belegt</i></td>
      </tr>
      </tbody>
    </table>

    <p>
      Quelle:
      <a href="https://de.wikipedia.org/wiki/Vorlage:Punktesystem_der_gymnasialen_Oberstufe" target="_blank">
        de.wikipedia.org/wiki/Vorlage:Punktesystem_der_gymnasialen_Oberstufe
      </a>
    </p>

    <h2>Berufsschule</h2>
    <table>
      <thead>
      <tr>
        <th>Note</th>
        <th>Notenwort</th>
        <th>BE</th>
        <th>Rohpunkte</th>
        <th>Notendefinition</th>
      </tr>
      </thead>
      <tbody>
      <tr class="green1">
        <td>1</td>
        <td>sehr gut</td>
        <td>{{ calc(max, 92) }}</td>
        <td>92%</td>
        <td><i>eine Leistung, die den Anforderungen in besonderem Maße entspricht</i></td>
      </tr>
      <tr class="green2">
        <td>2</td>
        <td>gut</td>
        <td>{{ calc(max, 81) }}</td>
        <td>81%</td>
        <td><i>eine Leistung, die den Anforderungen voll entspricht</i></td>
      </tr>
      <tr class="yellow1">
        <td>3</td>
        <td>befriedigend</td>
        <td>{{ calc(max, 67) }}</td>
        <td>67%</td>
        <td><i>eine Leistung, die im Allgemeinen den Anforderungen entspricht</i></td>
      </tr>
      <tr class="yellow2">
        <td>4</td>
        <td>ausreichend</td>
        <td>{{ calc(max, 50) }}</td>
        <td>50%</td>
        <td><i>eine Leistung, die zwar Mängel aufweist, aber im Ganzen den Anforderungen noch entspricht</i></td>
      </tr>
      <tr class="orange">
        <td>5</td>
        <td>mangelhaft</td>
        <td>{{ calc(max, 30) }}</td>
        <td>30%</td>
        <td>
          <i>
            eine Leistung, die den Anforderungen nicht entspricht, jedoch erkennen lässt, dass die notwendigen
            Grundkenntnisse vorhanden sind und die Mängel in absehbarer Zeit behoben werden können
          </i>
        </td>
      </tr>
      <tr class="red">
        <td>6</td>
        <td>ungenügend</td>
        <td>0</td>
        <td>0%</td>
        <td>
          <i>
            eine Leistung, die den Anforderungen nicht entspricht und selbst die Grundkenntnisse so lückenhaft sind,
            dass die Mängel in absehbarer Zeit nicht behoben werden können
          </i>
        </td>
      </tr>
      </tbody>
    </table>

    <p>
      Quelle:
      <a href="https://www.revosax.sachsen.de/vorschrift/17812-Schulordnung-Berufsschule#p22" target="_blank">
        www.revosax.sachsen.de/vorschrift/17812-Schulordnung-Berufsschule#p22
      </a>
    </p>
  </article>
</template>

<script setup>
import {ref} from 'vue';

let max = ref(100);

function calc(m, p) {
  return Math.round(m * p) / 100;
}

// const c = console;

// useHead({title: 'Noten'});

</script>

<script>
export default {
  name: 'NotenTable'
}
</script>

<style scoped lang="scss">
label {

  input {
    width: 5rem;
  }

  @media(min-width: 801px) {
    display: flex;
    flex-direction: row;
    column-gap: 1rem;
    align-items: center;
  }

  @media (max-width: 800px) {
    display: flex;
    flex-direction: column;
    row-gap: 1rem;
  }
}

table {
  width: 100%;
  display: block;
  overflow-x: auto;

  tr {
    &.green1,
    &.green2,
    &.yellow1,
    &.yellow2,
    &.orange,
    &.red {
      color: #000;
    }

    &.green1 {
      background-color: rgba(187 238 187 / 75%);
    }

    &.green2 {
      background-color: rgba(204 255 204 / 75%);
    }

    &.yellow1 {
      background-color: rgba(255 255 187 / 75%);
    }

    &.yellow2 {
      background-color: rgba(255 238 170 / 75%);
    }

    &.orange {
      background-color: rgba(255 221 170 / 75%);
    }

    &.red {
      background-color: rgba(255 170 170 / 75%);
    }

    td {
      padding: 0.2rem 0.5rem;
      text-align: center;
    }
  }
}

a {
  word-wrap: break-word;
}
</style>
