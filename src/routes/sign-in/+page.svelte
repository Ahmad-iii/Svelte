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
    background: linear-gradient(135deg, #eceff1 0%, #cfd8dc 100%);
    position: relative;
    overflow: hidden;
  }

  .response-container::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: linear-gradient(to right, #90a4ae, #607d8b);
  }

  .response-content {
    max-width: 600px;
    width: 90%;
    background: white;
    padding: 3rem;
    border-radius: 16px;
    text-align: center;
    box-shadow: 0 10px 25px rgba(96, 125, 139, 0.15);
    border: 1px solid rgba(96, 125, 139, 0.1);
    position: relative;
  }

  .response-content::before {
    content: '🔒';
    font-size: 48px;
    display: block;
    margin-bottom: 1.5rem;
    animation: shake 5s infinite;
    opacity: 0.7;
  }

  h1 {
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 32px;
    color: #455a64;
    margin-bottom: 1.5rem;
    text-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  }

  .message {
    font-family: 'Raleway', Arial, sans-serif;
    font-size: 18px;
    line-height: 1.6;
    color: #546e7a;
    margin-bottom: 2rem;
  }

  @keyframes shake {
    0%, 90%, 100% { transform: rotate(0); }
    92% { transform: rotate(-10deg); }
    94% { transform: rotate(10deg); }
    96% { transform: rotate(-10deg); }
    98% { transform: rotate(10deg); }
  }

  .back-button {
    display: inline-block;
    background: linear-gradient(135deg, #90a4ae 0%, #607d8b 100%);
    color: white;
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 16px;
    padding: 12px 32px;
    border-radius: 30px;
    text-decoration: none;
    transition: all 0.3s ease;
    border: none;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(96, 125, 139, 0.2);
  }

  .back-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(96, 125, 139, 0.3);
    background: linear-gradient(135deg, #78909c 0%, #546e7a 100%);
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
