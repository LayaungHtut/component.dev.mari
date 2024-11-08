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
                      src="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
                      alt="Skill_Blazing_Enlightenment"
                      width="100%"
                      height="100%"
                    />
                  </div>
                  <div class="accordionSkill">
                    <p>Blazing Brilliance</p>
                    <p>Basic Attack</p>
                  </div>
                </div>
              </td>

              <td>
                <p class="accordionSkillDescription">
                  Changli performs up to 4 consecutive attacks, dealing Fusion
                  DMG. After releasing Basic Attack 4, enter True Sight, lasting
                  for 12s.
                </p>

                <div id="accordion-more-1">
                  <!-- Basic Attack -->

                  <h4>Basic Attack</h4>

                  <p>
                    Changli performs up to 4 consecutive attacks, dealing Fusion
                    DMG. After releasing Basic Attack 4, enter True Sight,
                    lasting for 12s.
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
                    Hold Basic Attack on the ground to perform an upward strike
                    at the cost of Stamina, dealing Fusion DMG. Use Basic Attack
                    within a certain time to release Mid-Air Attack 3.
                  </p>

                  <!-- Mid-air Heavy Attack -->

                  <h4>Mid-air Heavy Attack</h4>

                  <p>
                    Shortly after holding Basic Attack in mid-air or using Basic
                    Attack True Sight, use Basic Attack to perform a plunging
                    attack at the cost of Stamina, dealing Fusion DMG. Use Basic
                    Attack within a certain time to release Basic Attack 3.
                  </p>

                  <!-- Dodge Counter -->

                  <h4>Dodge Counter</h4>

                  <p>
                    Use Basic Attack after a successful Dodge to attack the
                    target, dealing Fusion DMG.
                  </p>
                </div>
                <button>See More</button>
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
        display: flex;
        background-color: #ffffff;
        border-radius: 8px;
        overflow: hidden;

        & .accordion-content {
          & .accordionSkillImage {
            background-color: var(--black-800);
            border-radius: 8px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 10px;
            max-height: 100px;
          }

          & .accordionHeader {
            display: flex;
            flex-direction: row;
            align-items: center;
          }

          & table {
            width: 100%;
            max-width: 100%;
          }

          & table,
          td {
            border: 4px solid #c5c5c5;
            border-radius: 8px;
            padding: 10px;
          }

          & button {
            background-color: #1e1e1e;
            color: #fff;
            padding: 10px 20px;
            text-align: center;
            cursor: pointer;
            border: none;
            font-size: 14px;
            margin-top: 10px;
            width: 100%;
            border-radius: 20px;
            transition: background-color 0.3s ease;

            &:hover {
              background-color: hsla(0, 0%, 0%, 0.755);
            }
          }

          & .accordionSkill {
            flex-direction: row;
          }

          & .accordionSkillDescription {
            text-align: left;
            max-width: 100%;
            font-size: 20px;
            font-weight: 500;
          }

          & #accordion-more-1 {
            display: none;
          }
        }
      }
    }
  }
</style>
