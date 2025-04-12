<script lang="ts">
  export let title: string;
  export let description: string;
  export let align: string = 'left';
  export let pt: string = '4rem';
  export let maxwidth='500px'

</script>

<style>


  .hero h1 {
    font-size: 92px;
    font-weight: 400;
    line-height: 1.6;
    background: linear-gradient(45deg, var(--white), var(--gray));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }

  .hero p {
    font-size: 18px;
    color: var(--gray);
    line-height: 27px;
    margin-bottom: 3rem;
  }

  @media (max-width: 768px) {
    .hero {
      margin: 0 auto;
      text-align: center;
    }

    .hero h1 {
      font-size: 3.5rem;
    }

    .hero p {
      font-size: 1.25rem;
    }
  }
</style>
<section class="hero" style=" max-width:{maxwidth} ;padding-top: {pt}; text-align:{align}">

  <h1>{title}</h1>
  <p>{description}</p>
</section>
