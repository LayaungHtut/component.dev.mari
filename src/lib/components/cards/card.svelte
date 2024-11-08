<script lang="ts">
  interface LatestcardInterface {
    // Config
    cardHeaderSource: string;
    cardImageSource: string;
    cardContentSource: string;

    cardFooterToggle?: boolean;
    cardFooterSource?: string;

    cardSubHeader?: string;

    // Style
    cardImageWidth?: string;
    cardImageHeight?: string;
    cardImageAspectRatio?: number;

    cardTextColor?: string;
    cardBorderRadius?: string;
  }

  let {
    //Config
    cardHeaderSource = "Blackshore: To the shore’s end",
    cardImageSource = "https://s1.zerochan.net/Frieren.600.4172163.jpg",
    cardContentSource = "This is how description of the content looks like. Latest characters, weapons and storyline, bla bla bla..",
    cardSubHeader = "Latest Card",

    cardFooterToggle = true,
    cardFooterSource = "Go To This Page",

    // Style
    cardImageWidth = "100%",
    cardImageHeight = "100%",
    cardImageAspectRatio = 1 / 1.35,

    cardTextColor = "rgba(30, 30, 30, 0.747)",
    cardBorderRadius = "0.7rem",
  }: LatestcardInterface = $props();
</script>

<main>
  <div class="card" style={cardBorderRadius}>
    <div class="card-image" style="aspect-ratio: {cardImageAspectRatio};">
      <img
        src={cardImageSource}
        alt={cardImageSource}
        style="width: {cardImageWidth}; height: {cardImageHeight}; object-fit: cover;"
      />
    </div>
    <div class="card-content">
      <h4>{cardSubHeader}</h4>
      <h1>{cardHeaderSource}</h1>

      <p style="color: {cardTextColor};">
        {cardContentSource}
      </p>

      <p style="color: {cardTextColor};">
        {cardContentSource}
      </p>
      {#if cardFooterToggle === true}
        <button>{cardFooterSource}</button>
      {/if}
    </div>
  </div>
</main>

<style>
  main {
    display: flex;

    & .card {
      display: flex;
      flex-direction: column;
      height: 100%;
      border: 0.0625rem solid #838282;
      max-width: 55%;

      & .card-image {
        height: 100%;
        cursor: pointer;
        overflow: hidden;

        & img {
          transition: all 0.8s ease;
          box-shadow: 0.0625rem 0.125rem 0.0625rem 0.0625rem rgba(0, 0, 0, 0.2);

          &:hover {
            transform: scale(1.3);
          }
        }
      }

      & .card-content {
        display: flex;
        flex-direction: column;
        margin-left: 5%;

        & p {
          width: 90%;
          text-align: left;
          margin-top: 1.875rem;
          margin-bottom: 1.25rem;
          font-size: 1.25rem;
        }

        & button {
          cursor: pointer;
          padding: 0.625rem 4.375rem;
          border-radius: 1.25rem;
          font-size: 0.9375;
          border: 0.0625 solid #b3b3b3;
          background-color: #000000;
          color: #f2f2f2;
          transition: all 0.3s ease;
          width: 90%;
          margin: 0.625rem 0.625rem 1.25rem 0rem;

          &:hover {
            background-color: #333333;
          }
        }
      }
    }
  }

  @media screen and (min-width: 75rem) {
    main {
      & .card {
        flex-direction: row;
      }
    }
  }
</style>
