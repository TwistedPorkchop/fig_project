<script>
    import Logo from '../../lib/images/FIG_Logo.png'
    import Assasin from '../../lib/images/assassin.png'
    import Resident from '../../lib/images/resident.png'
    import Elden from '../../lib/images/elden.png'
    import AD from '../../lib/images/PS_ad.png'
    
    import Payment from '../../comp/Payment.svelte'
</script>
  <svelte:head>
	<title>Home</title>
	<meta name="description" content="HomePage" />
  <script src="https://www.paypal.com/sdk/js?client-id=YOUR_CLIENT_ID" data-namespace="paypal_sdk"></script>
  </svelte:head>


  <div class="header">
    <div class="header__logo"></div>
    <div class="header__buttons">
      <button class="header__button">Home</button>
      <button class="header__button">New Releases</button>
      <button class="header__button">Hot Deals</button>
    </div>
    <button class="header__cart">Cart</button>
  </div>
  
  <main class="page">

    <div class="ad">
      <a href="https://www.playstation.com" target="_blank" rel="noreferrer">
        <img src={AD} alt="No ADS!!?" />
      </a>
    </div>

    <div class="content">

      <div class="main">
        <section class="featured-games">
          <h2>Jeux en vedette</h2>
          <ul>
            <li>
              <img src={Assasin} alt="Game 1">
              <h3>Assassin's Creed Brotherhood</h3>
              <p>Jeu très assassin</p>
              <p class="price">19,99€</p>
            </li>
            <li>
              <img src={Resident} alt="Game 2">
              <h3>Resident Evil</h3>
              <p>Moscou Voyage</p>
              <p class="price">14,99€</p>
            </li>
            <li>
              <img src={Elden} alt="Game 3">
              <h3>Elden Ring</h3>
              <p>Anneau eld</p>
              <p class="price">29,99€</p>
            </li>
          </ul>
        </section>

        <Payment />
      </div>
      


    </div>
  </main>
  

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
    z-index: 1;
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
    height: 200vh;
    top: 50px;
    border-radius: 5px;
    border-color: pink;
    display: flex;
    flex-direction: column;
  }
  .content{
    width: 100%;
    height: max-content;
    display: flex;
    flex-direction: row;
  }

  /* styles for the ad space */
  .ad{
    width: 100%;
    height: 300px;
    border: 1px solid white;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0);
    color: white;
  }
  .ad img{
    width: fit-content;
    height: 100%;
    
  }

  /* styles for the main body */
  .main {
    width: 80%;
    border: 1px solid white;
    height: 100%;
    margin: 50px;
    padding: 50px;
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

  h2 {
    font-size: 32px;
    font-weight: bold;
    margin-bottom: 20px;
  }

  .featured-games ul,
  .latest-releases ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  .featured-games li,
  .latest-releases li {
    width: 30%;
    margin-bottom: 30px;
    position: relative;
    transition: all 0.2s ease-in-out;
    display: flex;
  }

  .featured-games li:hover,
  .latest-releases li:hover {
    transform: scale(1.1);
  }

  .featured-games li img,
  .latest-releases li img {
    width: 100%;
    display: block;
    border-radius: 5px;
  }

  .featured-games li h3,
  .latest-releases li h3 {
    font-size: 24px;
    font-weight: bold;
    margin: 10px 0;
  }

  .featured-games li p,
  .latest-releases li p {
    font-size: 16px;
    line-height: 1.5;
  }

  .price {
    font-size: 20px;
    font-weight: bold;
    position: absolute;
    bottom: 0;
    right: 0;
    margin: 10px;
    background-color: #333;
    color: #fff;
    padding: 5px 10px;
    border-radius: 5px;
  }

  .price::before {
    content: "€";
  }

  @media screen and (max-width: 768px) {
    .featured-games li,
    .latest-releases li {
      width: 100%;
    }
  }

  img {
    width: 30%;
    margin-bottom: 30px;
    position: relative;
    transition: all 0.2s ease-in-out;
    }
  </style>