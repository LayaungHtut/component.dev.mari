<script lang="ts">
  interface accordionInterface {
    // Config
    accordionSkillSource: string;
    accordionImageSource: string;
    accordionSkillDescriptionSource: string;

    accordionToggle: boolean;

    // Style
    accordionImageWidth: string;
    accordionImageHeight: string;
  }

  let {
    //Config
    accordionSkillSource = "Skill",
    accordionImageSource = "image",
    accordionSkillDescriptionSource = "Without accordion",

    // Style
    accordionImageWidth = "",
    accordionImageHeight = "",

    // Function
  }: accordionInterface = $props();

  let accordionToggle = $state(false);

  function toggleAccordion() {
    accordionToggle = !accordionToggle;
  }
</script>

<main>
  <div class="accordion">
    <div class="accordion-item">
      <div class="accordion-content">
        <table>
          <tbody>
            <tr>
              <td>
                <div class="accordionHeader">
                  <div class="accordionSkillImage" style="aspect-ratio: 1/1;">
                    <img
                      src={accordionImageSource}
                      alt={accordionImageSource}
                      width={accordionImageWidth}
                      height={accordionImageHeight}
                    />
                  </div>
                  <div class="accordionSkill">
                    <!-- <p>Blazing Brilliance</p>
                    <p>Basic Attack</p>
                  </div> -->
                    {accordionSkillSource}
                  </div>
                </div>
              </td>

              <td>
                {#if accordionToggle === false}
                  <p class="accordionSkillDescription">
                    {accordionSkillDescriptionSource}
                  </p>
                {/if}

                {#if accordionToggle}
                  <div class="accordion-more">
                    <!-- Basic Attack -->

                    <h4>Basic Attack</h4>

                    <p>
                      Changli performs up to 4 consecutive attacks, dealing
                      Fusion DMG. After releasing Basic Attack 4, enter True
                      Sight, lasting for 12s.
                    </p>

                    <!-- Mid-air Attack -->

                    <h4>Mid-air Attack</h4>

                    <p>
                      Changli consumes <a
                        href="https://wutheringwaves.fandom.com/wiki/Stamina"
                        >Stamina</a
                      > to perform up to 4 consecutive attacks in mid-air, dealing
                      Fusion DMG. After releasing Mid-Air Attack 4, enter True Sight,
                      lasting for 12s.
                    </p>

                    <!-- Heavy Attack -->

                    <h4>Heavy Attack</h4>

                    <p>
                      Hold Basic Attack on the ground to perform an upward
                      strike at the cost of Stamina, dealing Fusion DMG. Use
                      Basic Attack within a certain time to release Mid-Air
                      Attack 3.
                    </p>

                    <!-- Mid-air Heavy Attack -->

                    <h4>Mid-air Heavy Attack</h4>

                    <p>
                      Shortly after holding Basic Attack in mid-air or using
                      Basic Attack True Sight, use Basic Attack to perform a
                      plunging attack at the cost of Stamina, dealing Fusion
                      DMG. Use Basic Attack within a certain time to release
                      Basic Attack 3.
                    </p>

                    <!-- Dodge Counter -->

                    <h4>Dodge Counter</h4>

                    <p>
                      Use Basic Attack after a successful Dodge to attack the
                      target, dealing Fusion DMG.
                    </p>
                  </div>
                {/if}
                <button onclick={toggleAccordion}>
                  {accordionToggle ? "See Less" : "See More"}
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</main>

<style>
  main {
    & .accordion {
      & .accordion-item {
        border-radius: 0.5rem;

        & .accordion-content {
          & .accordionSkillImage {
            background-color: #1e1e1e;
            border-radius: 0.5rem;
            display: none;
            justify-content: center;
            align-items: center;
            max-height: 10rem;
          }

          & .accordionHeader {
            display: flex;
            flex-direction: row;
            align-items: center;
          }

          & table,
          td {
            border: 0.25rem solid #c5c5c5;
            border-radius: 0.5rem;
            padding: 0.625rem;
            max-width: 100%;
          }

          & button {
            background-color: #1e1e1e;
            color: #fff;
            padding: 0.3rem;
            text-align: center;
            cursor: pointer;
            border: none;
            font-size: 20px;
            margin-top: 0.625rem;
            width: 100%;
            border-radius: 1.25rem;
            transition: background-color 0.3s ease;

            &:hover {
              background-color: hsla(0, 0%, 0%, 0.755);
            }
          }

          & .accordionSkill {
            flex-direction: row;
            font-size: 1.25rem;
            max-width: 100%;
          }

          & .accordionSkillDescription {
            text-align: left;
            max-width: 100%;
            font-size: 1.25rem;
            font-weight: 500;
          }

          & .accordion-more {
            display: block;
            font-size: 1.25rem;
          }
        }
      }
    }
  }

  @media screen and (min-width: 75rem) {
    main {
      & .accordion {
        & .accordion-item {
          & .accordion-content {
            & .accordionSkillImage {
              display: flex;
            }
          }
        }
      }
    }
  }
</style>
