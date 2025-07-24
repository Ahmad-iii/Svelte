<div class="response-container">
  <div class="response-content">
    <h1>Registration Status</h1>
    <p class="message">We are not hiring new members right now, you will soon be able to register a new account</p>
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
    background: linear-gradient(135deg, #fff9c4 0%, #fff3e0 100%);
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
    background: linear-gradient(to right, #ffd54f, #ffb74d);
  }

  .response-content {
    max-width: 600px;
    width: 90%;
    background: white;
    padding: 3rem;
    border-radius: 16px;
    text-align: center;
    box-shadow: 0 10px 25px rgba(255, 183, 77, 0.15);
    border: 1px solid rgba(255, 183, 77, 0.1);
    position: relative;
  }

  .response-content::before {
    content: '⏳';
    font-size: 48px;
    display: block;
    margin-bottom: 1.5rem;
    animation: pulse 2s infinite;
  }

  h1 {
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 32px;
    color: #f57f17;
    margin-bottom: 1.5rem;
    text-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  }

  .message {
    font-family: 'Raleway', Arial, sans-serif;
    font-size: 18px;
    line-height: 1.6;
    color: #795548;
    margin-bottom: 2rem;
  }

  @keyframes pulse {
    0% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.1); opacity: 0.8; }
    100% { transform: scale(1); opacity: 1; }
  }

  .back-button {
    display: inline-block;
    background: linear-gradient(135deg, #ffd54f 0%, #ffb74d 100%);
    color: #5d4037;
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 16px;
    padding: 12px 32px;
    border-radius: 30px;
    text-decoration: none;
    transition: all 0.3s ease;
    border: none;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(255, 183, 77, 0.2);
  }

  .back-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(255, 183, 77, 0.3);
    color: #3e2723;
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
