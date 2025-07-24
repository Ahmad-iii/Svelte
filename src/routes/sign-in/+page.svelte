<div class="response-container">
  <div class="response-content">
    <h1>Sign In</h1>
    <p class="message">Apologies! Your account is in suspended list because of your inactivity, contact senior advisors for more information</p>
    <button class="back-button" on:click={goToHome}>Return to Home</button>
  </div>
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&display=swap');

  .response-container {
    min-height: 100vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    background-color: #f8f9fa;
  }

  .response-content {
    max-width: 600px;
    width: 90%;
    background: white;
    padding: 3rem;
    border-radius: 16px;
    text-align: center;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

  h1 {
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 32px;
    color: rgb(1, 22, 39);
    margin-bottom: 1.5rem;
  }

  .message {
    font-family: 'Raleway', Arial, sans-serif;
    font-size: 18px;
    line-height: 1.6;
    color: rgba(1, 22, 39, 0.8);
    margin-bottom: 2rem;
  }

  .back-button {
    display: inline-block;
    background: #515CD5;
    color: white;
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 16px;
    padding: 12px 32px;
    border-radius: 30px;
    text-decoration: none;
    transition: background-color 0.2s ease;
  }

  .back-button:hover {
    background: #6EC1E4;
  }

  @media (max-width: 480px) {
    .response-content {
      padding: 2rem;
    }

    h1 {
      font-size: 24px;
    }

    .message {
      font-size: 16px;
    }
  }
</style>

<script lang="ts">
  import { goto } from '$app/navigation';

  function goToHome(): void {
    goto('/');
  }
</script>
