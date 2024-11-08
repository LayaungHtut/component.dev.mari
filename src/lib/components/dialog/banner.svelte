<script lang="ts">
  interface bannerInterface {
    // Config
    bannerType: "default" | "button" | "cookies";

    bannerHeader?: "default" | "button" | "cookies";
    bannerHeaderSource?: string;

    bannerContent?: "default" | "button" | "cookies";
    bannerContentSource?: string;

    bannerFooter?: "default" | "button" | "cookies";
    bannerFooterSource?: string;

    // Style
    bannerBackground?: string;
    bannerBorder?: string;
  }

  let {
    //Config
    bannerType = "cookies",

    bannerHeader = "cookies",
    bannerHeaderSource = "🍪 Cookie Time!",

    bannerContent = "cookies",
    bannerContentSource = "Accept the cookie! NOW!",

    bannerFooter = "cookies",
    bannerFooterSource = "Accept Cookie",

    // Style
    bannerBackground = "#f2f2f2",
    bannerBorder = "2px solid #b3b3b3",
  }: bannerInterface = $props();
</script>

<main>
  <div
    class="banner"
    style="background-color: {bannerBackground}; border: {bannerBorder};"
  >
    <!-- Headers -->

    {#if bannerHeader === "cookies"}
      <div class="banner-header">
        <p>{bannerHeaderSource}<span>&times;</span></p>
      </div>
    {:else if bannerHeader === "button"}
      <div class="banner-header">
        <p>{bannerHeaderSource}<span>&times;</span></p>
      </div>
    {:else if bannerHeader === "default"}
      <div class="banner-header">
        <p>{bannerHeaderSource}<span>&times;</span></p>
      </div>
    {/if}

    <!-- Contents -->

    {#if bannerContent === "cookies"}
      <div class="banner-content">
        <p>{bannerContentSource}</p>
      </div>
    {:else if bannerContent === "button"}
      <div class="banner-content">
        <p>{bannerContentSource}</p>
      </div>
    {:else if bannerContent === "default"}
      <div class="banner-content">
        <p>{bannerContentSource}</p>
      </div>
    {/if}

    <!-- Footers -->

    {#if bannerFooter === "cookies"}
      <div class="banner-footer">
        <button>{bannerFooterSource}</button>
      </div>
    {:else if bannerFooter === "button"}
      <div class="banner-footer">
        <button>{bannerFooterSource}</button>
      </div>
    {:else if bannerFooter === "default"}
      <div class="banner-footer">
        <button>{bannerFooterSource}</button>
      </div>
    {/if}
  </div>
</main>

<style>
  main {
    width: 30rem;

    & .banner {
      display: flex;
      flex-direction: column;
      width: 100%;
      border-radius: 5px;

      & .banner-header {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        border-bottom: 2px solid #b3b3b3;
        height: 3.5rem;

        & p {
          & span {
            position: relative;
            align-self: center;
            right: -10rem;
            font-size: 30px;
            font-weight: 900;
            cursor: pointer;
          }
        }
      }

      & .banner-content {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        border-bottom: 2px solid #b3b3b3;
        height: 100px;
      }

      & .banner-footer {
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
