<main>
  <div class="banner">
    <div class="banner-header">
      <p>🍪Cookie Time! <span>&times;</span></p>
    </div>

    <div class="banner-content">
      <p>Accept the cookie! NOW!</p>
    </div>

    <div class="banner-footer">
      <button>Accept no Cookie</button>
    </div>
  </div>
</main>

<style>
  main {
    width: 40%;
    background-color: #f2f2f2;

    & .banner {
      display: flex;
      flex-direction: column;
      width: 100%;
      border: 2px solid #b3b3b3;
      border-radius: 5px;

      & .banner-header {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        border-bottom: 2px solid #b3b3b3;
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
          transition: background-color 0.3s ease-in-out;
        }

        & button:hover {
          background-color: #1e1e1e;
        }
      }
    }
  }
</style>
