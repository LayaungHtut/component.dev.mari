<script lang="ts">
  interface tableInterface {
    // Config
    tableDataSource: any[];

    tableAlterRowStripedToggle?: boolean;

    // Style
    tableBackgroundStrip?: string;
    tableBorder?: string;
  }

  let {
    //Config
    tableDataSource = [
      { level: 1, atk: 47, critDmg: "10.8%" },
      { level: 20, atk: 122, critDmg: "19.1%" },
      { level: 40, atk: 232, critDmg: "27.5%" },
      { level: 60, atk: 457, critDmg: "47.5%" },
    ],

    tableAlterRowStripedToggle = true,

    // Style
    tableBackgroundStrip = "#f2f2f2",
    tableBorder = "1px solid #e3e3e3",
  }: tableInterface = $props();
</script>

<main>
  {#if tableAlterRowStripedToggle === true}
    <table style="border: {tableBorder};">
      <thead>
        <tr>
          {#each Object.keys(tableDataSource[0]) as header}
            <th>{header.charAt(0).toUpperCase() + header.slice(1)}</th>
          {/each}
        </tr>
      </thead>
      <tbody>
        {#each tableDataSource as row, index}
          <tr>
            {#each Object.values(row) as cell}
              <td>{cell}</td>
            {/each}
          </tr>
        {/each}
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
