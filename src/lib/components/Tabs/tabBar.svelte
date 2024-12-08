<script lang="ts">
  interface tabBarInterface {
    //Config
    tabsDescription: { heading: string; content: string }[];

    // Style
  }

  let {
    tabsDescription = [],
  }: tabBarInterface = $props();

  let activeTab = $state(0);

  const handleTabClick = (index: number) => {
    activeTab = index;
  };
</script>

<main>
  <div class="tabContainer">
    <div class="tabHeader">
      {#each tabsDescription as tab, index}
        <button
          class="tabBtn {index === activeTab ? 'active' : ''}"
          ondblclick={() => handleTabClick(index)}
        >
          {tab.heading}</button
        >
      {/each}
      <div
        class="tabLiner"
        style="transform: translateX({activeTab * 100}%)"
      ></div>
    </div>

    <div class="tabContent">
      {#each tabsDescription as tab, index}
        <div class="content {index === activeTab ? 'active' : ''}">
          {tab.content}
        </div>
      {/each}
    </div>
  </div>
</main>

<style>
  main {
    & .tabContainer {
      & .tabHeader {
        position: relative;
        display: flex;
        justify-content: space-around;
        width: 100%;
        background-color: rgba(250, 249, 253, 1);
        box-shadow: 1px 3px 3px rgba(0, 0, 0, 0.1);

        & .tabBtn {
          border: none;
          padding: 10px 20px;
          cursor: pointer;
          color: rgba(0, 0, 0, 1);
          font-size: 16px;
          transition: all 0.5s ease;
          text-align: center;
          width: 100%;
          background-color: rgba(250, 249, 253, 1);

          &:hover {
            background-color: rgba(237, 236, 236, 1);
          }

          &.active {
            background-color: #f8f9fa;
            font-weight: bold;
            transition: all 0.5s ease;
          }
        }

        & .tabLiner {
          position: absolute;
          bottom: 0;
          left: 0;
          height: 4px;
          width: 31.25rem;
          border-radius: 20px;
          background-color: rgba(90, 170, 212, 1);
          transition: all 0.3s ease;
        }
      }

      & .tabContent {
        & .content {
          padding: 50px;
          display: none;
          animation: moving 0.5s ease-in-out;

          @keyframes moving {
            from {
              transform: translateX(50px);
              opacity: 0;
            }

            to {
              transform: translateX(0);
              opacity: 1;
            }
          }

          &.active {
            display: block;
          }
        }
      }
    }
  }
</style>
