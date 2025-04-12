<script lang="ts">
import Button from "../buttons/button.svelte";

    export let title: string = "Contact Us";
    export let description: string = "Reach out to us with any questions, ideas, or partnership inquiries.";
  </script>
  
  <style>
    .contact-wrapper {
      display: flex;
      flex-direction: column;
      align-items: center;
      background: var(--black);
      padding: 4rem 2rem;
      border: 1px solid var(--grayfaded);
      border-radius: 16px;
      max-width: 700px;
      margin: 0 auto;
    }
  
    h1 {
      font-size: 48px;
      background: linear-gradient(45deg, var(--white), var(--gray));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 1rem;
      text-align: center;
    }
  
    p {
      color: var(--gray);
      font-size: 18px;
      text-align: center;
      margin-bottom: 2rem;
      max-width: 600px;
    }
  
    form {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      width: 100%;
    }
  
    input, textarea {
      background-color: var(--faded);
      color: var(--white);
      padding: 1rem;
      border: 1px solid var(--grayfaded);
      border-radius: 8px;
      font-size: 1rem;
      resize: none;
    }
  
    input:focus, textarea:focus {
      outline: none;
      border-color: var(--white);
    }
  
    button {
      background: var(--white);
      color: var(--black);
      padding: 0.75rem 1.5rem;
      font-weight: bold;
      border-radius: 8px;
      cursor: pointer;
      align-self: center;
      transition: all 0.3s ease-in-out;
    }
    .nav-btn {
          background: var(--white);

      border: 1px solid white;
          padding: 0.5rem 1rem;
          border-radius: 9999px;
          color: var(--black);
          width: 150px;
          height: 50px;
          /* margin-top: -30px; */
          font-weight: normal;
          cursor: pointer;
        }
    button:hover {
        background-color: var(--black);
        color: var(--white);
    }
  
    @media (max-width: 768px) {
      h1 {
        font-size: 36px;
      }
  
      p {
        font-size: 16px;
      }
  
      .contact-wrapper {
        padding: 3rem 1rem;
      }
    }
  </style>
  
  <section class="contact-wrapper">
    <h1>{title}</h1>
    <p>{description}</p>
  
    <form on:submit|preventDefault={() => console.log('Form submitted')}>
      <input type="email" placeholder="Your email address" required />
      <textarea rows="5" placeholder="How can we help you?" required />
      
      <button class="nav-btn" type='sumbit' >Get Started</button>
    </form>
  </section>
  