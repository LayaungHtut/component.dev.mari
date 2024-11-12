<script lang="ts">
  interface ResonatorInterface {
    // Config
    cardTitle: string;

    resonatorStarsRating: string;
    resonatorStarsSource: string;

    resonatorNameSource: string;
    resonatorImageSource: string;

    resonatorElementSource: string;
    resonatorWeaponSource: string;

    resonatorElementIconSource: string;
    resonatorWeaponIconSource: string;
    // Style
  }

  let {
    //Config
    cardTitle = "",

    resonatorStarsRating = "",
    resonatorStarsSource = "",

    resonatorNameSource = "",
    resonatorImageSource = "",

    resonatorElementSource = "",
    resonatorWeaponSource = "",

    resonatorElementIconSource = "",
    resonatorWeaponIconSource = "",

    // Style
  }: ResonatorInterface = $props();
</script>

<main>
  <div class="resonator">
    <div class="resonatorCardComponent">
      <div class="resonatorImage">
        <img src={resonatorImageSource} alt="" width="400px" height="400px" />
      </div>

      <h3>{cardTitle}</h3>
      <div class="resonatorRating">
        <span class="rating-stars">{resonatorStarsRating}</span
        >{resonatorStarsSource} Stars
      </div>

      <div class="resonatorDescription">
        <h4>{resonatorNameSource}</h4>

        <p class="resonatorUsage">
          Weapon: <img
            class="usageIcon"
            src={resonatorWeaponIconSource}
            alt=""
          />
          {resonatorWeaponSource}
        </p>

        <p class="resonatorUsage">
          Element: <img
            class="usageIcon"
            src={resonatorElementIconSource}
            alt=""
          />
          {resonatorElementSource}
        </p>
      </div>

      <button>See More</button>
    </div>
  </div>
</main>

<style>
  main {
    & .resonator {
      & .resonatorCardComponent {
        border: 0.0625rem solid #a6a6a6;

        max-width: max-content;
        max-height: max-content;

        & .resonatorImage {
          background-color: #fff;
          cursor: pointer;
          overflow: hidden;
          /*  max-height: 100%;
          max-width: 100%; */

          border-bottom: 0.0625rem solid #a6a6a6;

          & img {
            transition: all 0.6s ease;
            /* width: 100%;
            max-height: 100%; */

            &:hover {
              transform: scale(1.3);
            }
          }
        }

        & h3 {
          text-align: left;
          margin: 0.5rem 0.9375rem 0.625rem 0.625rem;
        }

        & .resonatorRating {
          & span {
            color: #ffd700;
            margin-left: 0.625rem;
            font-size: 1.6875rem;
            text-shadow: 0.125rem 0.125rem 0.125rem rgba(0, 0, 0, 0.2);
            margin-right: 0.3125rem;
          }
        }

        & .resonatorDescription {
          & h4 {
            margin: 0.625rem;
            font-size: 1.25rem;
          }

          & .resonatorUsage {
            display: flex;
            align-items: center;

            & .usageIcon {
              width: 1.5625rem;
              height: 1.5625rem;
              display: flex;
            }
          }
        }

        & button {
          cursor: pointer;
          border: none;
          background-color: #1e1e1e;
          color: #ffffff;
          border-radius: 1.25rem;

          width: 90%;
          padding: 0.3125rem 4.375rem;
          font-size: 1.0625rem;

          font-weight: 400;
          transition: background-color 0.3s ease;
          margin: 0.625rem 0.625rem 1.25rem 0.625rem;

          &:hover {
            background-color: #333333;
          }
        }
      }
    }
  }
</style>
