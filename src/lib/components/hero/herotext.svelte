<script lang="ts">
  export let title: string;
  export let description: string;
</script>

<style>
  .hero {
    padding-top: 4rem;
    text-align: left;
    max-width: 500px;
    width: 100%;
  }

  .hero h1 {
    font-size: 92px;
    font-weight: 400;
    line-height: 1.2;
    background: linear-gradient(45deg, var(--white), var(--gray));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    margin: 0;
  }

  .hero p {
    font-size: 18px;
    color: var(--gray);
    line-height: 27px;
    margin: 1rem 0 3rem 0;
  }

  @media (max-width: 968px) {
    .hero {
      max-width: 100%;
      padding-top: 2rem;
    }

    .hero h1 {
      font-size: 72px;
    }

    .hero p {
      font-size: 16px;
    }
  }

  @media (max-width: 768px) {
    .hero {
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding-left: 1rem;
      padding-right: 1rem;
      padding-top: 1rem ;
      padding-bottom: 2rem;
    }

    .hero h1 {
      font-size: 3rem;
    }

    .hero p {
      font-size: 1.2rem;
      line-height: 1.8rem;
    }
  }
</style>

<section class="hero">
  <h1>{title}</h1>
  <p>{description}</p>
</section>
