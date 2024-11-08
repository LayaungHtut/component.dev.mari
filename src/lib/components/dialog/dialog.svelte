<script lang="ts">
  import { fly } from "svelte/transition";

  interface dialogInterface {
    // Config
    dialogHeaderToggle?: boolean;
    dialogHeaderSource?: string;

    dialogContentSource?: string;

    dialogFooterToggle?: boolean;
    dialogFooterSource?: string;

    // Style
    dialogBackground?: string;
    dialogBorder?: string;

    // Function
    onActionButtonClick?: () => void | any;
  }

  let {
    //Config
    dialogHeaderToggle = true,
    dialogHeaderSource = "Header",

    dialogContentSource = "Content",

    dialogFooterToggle = true,
    dialogFooterSource = "Accept",

    // Style
    dialogBackground = "#f2f2f2",
    dialogBorder = "2px solid #b3b3b3",

    // Function
    onActionButtonClick = () => {},
  }: dialogInterface = $props();

  let isDialogVisible = $state(true);

  function onCloseButtonClick() {
    isDialogVisible = false;
  }
</script>

<main>
  {#if isDialogVisible}
    <div
      class="dialog"
      style="background-color: {dialogBackground}; border: {dialogBorder};"
      transition:fly={{ x: 300, duration: 1000 }}
    >
      <!-- Headers -->
      {#if dialogHeaderToggle === true}
        <div class="dialog-header">
          <p>{dialogHeaderSource}</p>
          <button onclick={onCloseButtonClick}>&times;</button>
        </div>
      {/if}

      <!-- Contents -->
      <div class="dialog-content">
        {dialogContentSource}
      </div>

      <!-- Footers -->

      {#if dialogFooterToggle === true}
        <div class="dialog-footer">
          <button onclick={onActionButtonClick}>{dialogFooterSource}</button>
        </div>
      {/if}
    </div>
  {/if}
</main>

<style>
  main {
    width: 30rem;

    & .dialog {
      display: flex;
      flex-direction: column;
      width: 100%;
      border-radius: 5px;

      & .dialog-header {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        border-bottom: 2px solid #b3b3b3;
        height: 3.5rem;

        & button {
          position: relative;
          border: none;
          align-self: center;
          right: -10rem;
          font-size: 40px;
          cursor: pointer;
        }
      }

      & .dialog-content {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        border-bottom: 2px solid #b3b3b3;
        height: 100px;
      }

      & .dialog-footer {
        display: flex;
        justify-content: right;

        & button {
          background: #1e1e1e;
          border: none;
          border-radius: 10px;
          padding: 8px 20px;
          color: whitesmoke;
          cursor: pointer;
          margin: 2%;
          transition: background-color 0.15s ease-in-out;
        }

        & button:hover {
          background-color: hsla(0, 0%, 12%, 0.9);
        }
      }
    }
  }
</style>
