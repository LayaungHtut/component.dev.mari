<script lang="ts">
  interface tableInterface {
    // Config
    level: number;
    atk: number;
    critDmg: number;

    tableToggle?: boolean;

    // Style
    tableBackgroundStrip?: string;
    tableBorder?: string;
  }

  let {
    //Config
    level = 1,
    atk = 47,
    critDmg = 10.8,

    tableToggle = true,

    // Style
    tableBackgroundStrip = "#f2f2f2",
    tableBorder = "1px solid #e3e3e3",
  }: tableInterface = $props();
</script>

<main>
  {#if tableToggle === true}
    <table style="border: {tableBorder};">
      <thead>
        <tr>
          <th>Level</th>
          <th>Atk</th>
          <th>Crit Dmg</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{level}</td>
          <td>{atk}</td>
          <td>{critDmg}</td>
        </tr>
        <tr>
          <td>20</td>
          <td>122</td>
          <td>19.1%</td>
        </tr>
        <tr>
          <td>40</td>
          <td>232</td>
          <td>27.5%</td>
        </tr>
        <tr>
          <td>60</td>
          <td>457</td>
          <td>47.5%</td>
        </tr>
      </tbody>
    </table>
  {/if}
</main>

<style>
  main {
    & table {
      border-collapse: collapse;
      width: 100%;
      text-align: center;
      border-radius: 25%;

      & th {
        background-color: #f2f2f2;
      }

      & tbody {
        & tr:nth-child(even) {
          background-color: #f2f2f2;
        }
      }
    }

    & th,
    & td {
      border: 1px solid #ddd;
      padding: 8px;
    }
  }
</style>
