<!-- App.svelte -->
<script>
    import SignIn from "./SignIn.svelte";

    let showLoginModal = false;
    let showSignupModal = false;
  
    function openLoginModal() {
      showLoginModal = true;
    }
  
    function closeLoginModal() {
      showLoginModal = false;
    }
  
    function openSignupModal() {
      showSignupModal = true;
    }
  
    function closeSignupModal() {
      showSignupModal = false;
    }
  </script>
  
  <div>
    <button on:click={openLoginModal} class="button button-login">Login</button>
    <button on:click={openSignupModal} class="button button-signup">Sign Up</button>
  
    {#if showLoginModal}
      <div class="modal">
        <h2>Login</h2>
        <!-- Add your login form here -->
        <button on:click={closeLoginModal}>Close</button>
      </div>
    {/if}
  
    {#if showSignupModal}
      <div class="modal">
        <h2>Sign Up</h2>
        <!-- Add your sign up form here -->
        <button on:click={closeSignupModal}>Close</button>
      </div>
    {/if}
  </div>
  
  <style>
  
    .button {
      display: inline-block;
      width: 8vw;
      padding: 10px 20px;
      font-size: 1em;
      border-radius: 50px;
      border: none;
      color: black;
      cursor: pointer;
    }
  
    .button-login {
      background-color: rgb(215, 1, 155);
    }
  
    .button-signup {
      background-color: rgb(246, 252, 138);
    }
  
    .modal {
      position: fixed;
      top: 25vh;
      left: 25vw;
      width: 50%;
      height: 50%;
      background-color: rgb(48, 45, 45);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 10;
    }
  
    .modal h2 {
      margin-top: 0;
    }
  
    .modal button {
      margin-top: 10px;
    }
  </style>
  