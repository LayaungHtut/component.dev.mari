<script lang="ts">
  interface tabBarInterface {
    //Config
    tabsDescription: { heading: string; content: any  }[];

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
          onclick={() => handleTabClick(index)}
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
        box-shadow: 0.0625rem 0.1875rem 0.1875rem rgba(0, 0, 0, 0.1);

        & .tabBtn {
          border: none;
          padding: 0.625rem 1.25rem;
          cursor: pointer;
          color: rgba(0, 0, 0, 1);
          font-size: 1rem;
          transition: all 0.5s ease;
          width: 100%;
          background-color: rgba(250, 249, 253, 1);
          
          
          &:hover {
            background-color: rgba(237, 236, 236, 1);
          }
          
          &.active {
            background-color: #f8f9fa;
            font-weight: bold;
            transition: all 0.3s ease-in-out;
            border-bottom: 0.1875rem solid rgba(90, 170, 212, 1);
          }
        }

        & .tabLiner {
          position: absolute;
          bottom: 0;
          left: 0;
          height: 0.25rem;
         /*  width: 31.25rem; */
          border-radius: 1.25rem;
          background-color: rgba(90, 170, 212, 1);
          transition: all 0.3s ease;
        }
      }

      & .tabContent {
        & .content {
          padding: 3rem;
          opacity: 0;
          transform: translateX(3.125rem);
          transition: all 0.5s ease-in-out;

          &.active {
            opacity: 1;
            transform: translateX(0);
          }
        }
      }
    }
  }
</style>

