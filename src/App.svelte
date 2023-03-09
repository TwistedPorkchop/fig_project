<script>
  import Logo from './assets/FIG_Logo.png'
  import Register from './Register.svelte';
</script>

<main>
  <div id="Main_Logo">
      <img src={Logo} alt="Oops No Logo"/>
  </div>
  <div id="Main_Login">
    <!-- Register pops up a log in or sign in screen for the user to fill in. Needs a on destroy method when clicked-->
      <Register />
      <!-- all buttons, Register and Browsing should take you the the main page. Could add tokne handling in the future -->
      <button id="Browsing">Just Browsing</button>
  </div>
</main>

<style>
  img{
    width: 20vw;
    height: max-content;
    border-radius: 25%;
  }
</style>
