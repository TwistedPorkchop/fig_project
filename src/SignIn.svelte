<script>
  import { onMount } from 'svelte';
  var zxcvbn = require('zxcvbn');
  zxcvbn('Tr0ub4dour&3');

  let firstName = '';
  let lastName = '';
  let email = '';
  let password = '';
  let showPassword = false;
  let passwordStrength = 0;
  let submitted = false;

  function checkPasswordStrength(psw) {
      console.log(psw);
      let result = zxcvbn(psw);
      return result.score;
  };

  const submitForm = (e) => {
    e.preventDefault();

    if (!firstName || !lastName || !email || !password) {
      alert('Please fill out all fields');
      return;
    }

    if (!/\S+@\S+\.\S+/.test(email)) {
      alert('Please enter a valid email address');
      return;
    }

    if (passwordStrength < 2) {
      alert('Password is too weak. Please enter a stronger password');
      return;
    }

    submitted = true;
    // Do something with the submitted data, e.g. submit to backend
  };

  onMount(() => {
    checkPasswordStrength();
  });
</script>

<form on:submit={submitForm} class="form-container">
  <div class="form-field">
    <label for="firstName">First Name</label>
    <input type="text" id="firstName" bind:value={firstName} required />
  </div>

  <div class="form-field">
    <label for="lastName">Last Name</label>
    <input type="text" id="lastName" bind:value={lastName} required />
  </div>

  <div class="form-field">
    <label for="email">Email Address</label>
    <input type="email" id="email" bind:value={email} required />
  </div>

  <div class="form-field">
    <label for="password">Password</label>
    <input type={showPassword ? "text" : "password"} id="password" value={password} required />
    <button type="button" on:click={() => showPassword = !showPassword}>
      {showPassword ? 'Hide' : 'Show'}
    </button>
  </div>

  <div class="form-field">
    <p>Password strength:</p>
    <span>{checkPasswordStrength(password)}</span>
  </div>

  <div class="form-field">
    <button type="submit" disabled={submitted}>
      {submitted ? 'Submitted!' : 'Submit'}
    </button>
  </div>

</form>



<style>
  .form-container{
      width: 80%;
      height: max-content;
      display: flex;
      flex-direction: column;
      align-content: space-between;
  }
  .form-field{
      margin: 5px;
      padding: 5px;
  }
</style>