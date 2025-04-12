<script lang="ts">
  export let faqs: { question: string; answer: string }[] = [];
  export let title: string = "Frequently Asked Questions";
  export let description: string = "Here are answers to some of the most common questions.";
  let openIndex: number | null = null;

  const toggle = (index: number) => {
    openIndex = openIndex === index ? null : index;
  };
</script>

<style>
  .faq-container {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    padding: 0rem 2rem 4rem;
    gap: 3rem;
    width: 100%;
    max-width: 1200px;
    margin: auto;
  }

  .faq-left {
    flex: 1;
    max-width: 500px;
  }

  .faq-left h1 {
    font-size: 3rem;
    line-height: 1.4;
    font-weight: 400;
    background: linear-gradient(45deg, var(--white), var(--gray));
    -webkit-background-clip: text;
    color: transparent;
  }

  .faq-left p {
    font-size: 1rem;
    color: var(--gray);
    margin-top: 1rem;
  }

  .faq-right {
    flex: 1.2;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .faq-item {
    background: var(--black);
    border: 1px solid var(--grayfaded);
    padding: 1rem 1.5rem;
    cursor: pointer;
    transition: background 0.3s ease;
  }

  .faq-item:hover {
    background: var(--faded);
  }

  .faq-question {
    font-size: 1.1rem;
    color: var(--white);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .faq-answer {
    margin-top: 0.5rem;
    font-size: 1rem;
    color: var(--gray);
    line-height: 1.5;
  }

  @media (max-width: 768px) {
    .faq-container {
      flex-direction: column;
    }
    .faq-left, .faq-right {
      width: 100%;
      max-width: 100%;
    }
    .faq-left h1 {
      text-align: center;
      font-size: 2.5rem;
    }
    .faq-left p {
      text-align: center;
    }
  }
</style>

<div class="faq-container">
  <div class="faq-left">
    <h1>{title}</h1>
    <p>{description}</p>
  </div>

  <div class="faq-right">
    {#each faqs as faq, index}
      <div class="faq-item" on:click={() => toggle(index)}>
        <div class="faq-question">
          <span>{faq.question}</span>
          <span>{openIndex === index ? '−' : '+'}</span>
        </div>
        {#if openIndex === index}
          <div class="faq-answer">{faq.answer}</div>
        {/if}
      </div>
    {/each}
  </div>
</div>
