<script lang="ts">
  import { slide } from "svelte/transition";

  interface accordionInterface {
    // Config
    accordionHeaderSource: string;

    accordionSkillSource: string;
    accordionImageSource: string;
    accordionSkillDescriptionSource: string;
    accordionMoreContent: string;

    accordionToggle: boolean;

    // Style
    accordionImageWidth: string;
    accordionImageHeight: string;
  }

  let {
    //Config
    accordionHeaderSource = "Header",
    accordionSkillSource = "Skill",
    accordionImageSource = "image",
    accordionSkillDescriptionSource = "Without accordion",
    accordionMoreContent = "More Content",

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
                  <div class="accordion-more" transition:slide|gloabl>
                    <h2>{accordionHeaderSource}</h2>
                    <p>{accordionMoreContent}</p>
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
            width: 10rem;
            height: 10rem;
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
            max-width: 80%;
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
            margin: 1rem;
          }

          & .accordionSkillDescription {
            text-align: left;
            max-width: 100%;
            font-size: 1.25rem;
          }

          & .accordion-more {
            display: block;
            font-size: 1.25rem;
            width: 100%;
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
