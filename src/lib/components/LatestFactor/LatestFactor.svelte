<script lang="ts">
  interface LatestFactorInterface {
    // Config
    factorHeader?: string;
    factorImage?: string;
    factorContent?: string;

    // Style
    factorImageWidth?: number;
    factorImageHeight?: number;

    textColor?: string;
  }

  let {
    //Config
    factorHeader = "Blackshore: To the shore’s end",
    factorImage = "https://static.wikia.nocookie.net/wutheringwaves/images/8/8b/Black_Shores_teaser.png/revision/latest/",
    factorContent = "This is how description of the content looks like. Latest characters, weapons and storyline, bla bla bla..",

    // Style
    factorImageWidth = 500,
    factorImageHeight = 400,

    textColor = "rgba(30, 30, 30, 0.747)",
  }: LatestFactorInterface = $props();
</script>

<main>
  <div class="latest-factor">
    <div class="factor-image">
      <img
        src={factorImage}
        alt="to the shore end"
        width={factorImageWidth + "px"}
        height={factorImageHeight + "px"}
      />
    </div>
    <div class="factor-content">
      <h1>Latest Factor</h1>
      <h2>{factorHeader}</h2>

      <p style="color: {textColor};">
        {factorContent}
      </p>

      <p style="color: {textColor};">
        {factorContent}
      </p>

      <button>Visit Profile</button>
    </div>
  </div>
</main>

<style>
  main {
    display: flex;

    & .latest-factor {
      display: flex;
      flex-direction: row;
      height: 100%;
      border: 1px solid #838282;
      border-radius: 10px;
      max-width: 55%;

      & .factor-image {
        width: 25%;
        height: 100%;
        cursor: pointer;

        & img {
          transition: all 0.3s ease;
          max-width: 100%;
          box-shadow: 1px 2px 1px 1px rgba(0, 0, 0, 0.2);

          &:hover {
            transform: scale(1.3);
          }
        }
      }

      & .factor-content {
        display: flex;
        flex-direction: column;
        margin-left: 5%;

        & p {
          width: 90%;
          text-align: left;
          margin-top: 30px;
          margin-bottom: 20px;
          font-size: 20px;
        }

        & button {
          cursor: pointer;
          padding: 5px 70px;
          border-radius: 20px;
          font-size: 15px;
          border: 1px solid #b3b3b3;
          background-color: #000000;
          color: #f2f2f2;
          transition: all 0.3s ease;
          width: 55%;
          margin: 10px 10px 20px 10px;

          &:hover {
            background-color: #333333;
          }
        }
      }
    }
  }
</style>
