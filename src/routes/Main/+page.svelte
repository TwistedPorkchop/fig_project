<script>
    import Logo from '../../lib/images/FIG_Logo.png'
    import Payment from '../../comp/Payment.svelte'
</script>
  
  <div class="header">
    <div class="header__logo"></div>
    <div class="header__buttons">
      <button class="header__button">Button 1</button>
      <button class="header__button">Button 2</button>
      <button class="header__button">Button 3</button>
      <button class="header__button">Button 4</button>
    </div>
    <button class="header__cart">Cart</button>
  </div>
  
  <div class="page">

    <div class="ad">
      Ad space
    </div>

    <div class="content">

      <div class="main">
        Main section
        <Payment />
      </div>
      
      <div class="sidebar">
        Sidebar section
      </div>

    </div>
  </div>
  

  <style>
    /* styles for the header */
    .header {
      position: sticky;
      top: 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px;
      background-color: black;
      color: purple;
    }
  
    .header__logo {
      width: 50px;
      height: 50px;
      background-image: url({logo});
      background-size: cover;
    }
  
    .header__buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }
  
    .header__button {
      padding: 10px;
      background-color: purple;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  
    .header__cart {
      padding: 10px;
      background-color: purple;
      color: white;
      border: none;
      border-radius: 50%;
      cursor: pointer;
    }
  
    /*Page layout styling*/
    .page{
      height: 100%;
      top: 50px;
      border-radius: 5px;
      border-color: pink;
      display: flex;
      justify-content: center;
      flex-direction: column;
    }
    .content{
      width: 100%;
      display: flex;
      flex-direction: row;
    }

    /* styles for the ad space */
    .ad{
      width: 100%;
      height: 100px;
      border: 1px solid white;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: black;
      color: white;
    }
  
    /* styles for the main body */
    .main {
      width: 80%;
      border: 1px solid white;
      height: 500px;
      margin: 20px;
      background-color: black;
      color: purple;
    }
  
    .sidebar {
      width: 20%;
      border: 1px solid white;
      height: 500px;
      margin: 20px;
      background-color: black;
      color: purple;
    }
  </style>