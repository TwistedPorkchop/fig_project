<script>
    import Logo from '../lib/images/FIG_Logo.png'   
    import Register from '../comp/Register.svelte';
  </script>
  
  <svelte:head>
	<title>Reception</title>
	<meta name="description" content="Reception Page" />
  </svelte:head>
  <main>
    <div id="Main_Logo">
        <img src={Logo} alt="Oops No Logo"/>
    </div>
    <div id="Main_Login">
      <!-- Register pops up a log in or sign in screen for the user to fill in. Needs a on destroy method when clicked-->
        <Register />
        <!-- all buttons, Register and Browsing should take you the the main page. Could add tokne handling in the future -->
        <nav>
            <a id="Browsing" href="/Main">Just Browsing</a>
        </nav>
    </div>
  </main>
  
  <style>
    img{
      width: 20vw;
      height: max-content;
      border-radius: 25%;
    }
    main{
    margin: 0;
    padding: 0;
    display: flex;
    place-items: center;
    justify-content: center;
    min-width: 100vw;
    min-height: 100vh;
    background-color: black;
    overflow: hidden;
    flex-direction: column;
    }
    nav{
      margin-top: 10px;
      margin-left: 27%;
      display: inline-block;
      width: 5vw;
      padding: 10px 20px;
      font-size: 1em;
      border-radius: 50px;
      border: none;
      background-color: gold;
      color: black;
      cursor: pointer;
      display:flex;
    }
  </style>
  