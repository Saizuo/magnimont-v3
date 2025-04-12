<script>
  export let height = '50px'; // default fallback
</script>

<style>
  .nav-btn {
    background: var(--white);
    border: 1px solid white;
    transition: all 0.3s ease-in-out;
    padding: 0.5rem 1rem;
    border-radius: 9999px;
    color: var(--black);
    width: 150px;
    /* margin-top: -30px; */
    font-weight: normal;
    cursor: pointer;
  }
  button:hover {
        background-color: var(--black);
        color: var(--white);
    }
/* @media screen (max-width:768px){
  .nav-btn{
    margin-top:-50px;

  }
} */

</style>

<button class="nav-btn" style="height: {height};">Get Started</button>
