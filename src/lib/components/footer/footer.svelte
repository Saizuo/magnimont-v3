<script lang="ts">
  import Logo from "$lib/assets/logo.svg";

  const footerLinks = {
    Magnimont: [
      { name: 'Host', href: 'https://host.magnimont.com/' },
      { name: 'Forums', href: 'https://forum.magnimont.com/' },
    ],
    Resources: [
      { name: 'Status', href: '#' },
      { name: 'Brand', href: '#' },
    ],
    Company: [
      { name: 'About', href: '#' },
      { name: 'Team', href: '/team' },
      { name: 'Careers', href: '/Careers' },
      { name: 'Contact', href: '#' },
    ],
    Handbook: [
      { name: 'Why we exist', href: '#' },
      { name: 'How we work', href: '#' },
      { name: 'Support', href: '/Support' },
    ],
    Legal: [
      { name: 'Cookie Policy', href: '/Cookie-Policy' },
      { name: 'Privacy Policy', href: '/Privacy-policy' },
      { name: 'Terms of Service', href: '/Terms-of-Service' },
    ],
  };
</script>

<footer>
  <div class="footer-container">
    <div class="logo">
      <img class="logoimg" src={Logo} alt="logo" />
      <span>Magnimont</span>
    </div>

    <div class="links-container">
      {#each Object.entries(footerLinks) as [category, links], i}
        <div class="link-block {i !== 0 ? 'bordered' : ''}">
          <h3>{category}</h3>
          <ul>
            {#each links as link}
              <li><a href={link.href}>{link.name}</a></li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>
  </div>
</footer>

<style>
  footer {
    background: black;
    padding: 0rem 1.5rem 0rem;
    margin-top: 8rem;
    font-family: 'Inter', sans-serif;
    color: var(--gray);
    /* border-top: 1px solid var(--faded); */
  }

  .footer-container {
    /* padding-top: 1rem; */
    max-width: 1280px;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    gap: 3rem;
    align-items: flex-start;
  }

  .logo {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    justify-content: flex-start;
    width: 200px;
  }

  .logoimg {
    height: 80px;
    width: 50px;
  }

  .logo span {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--white);
  }

  .links-container {
    display: flex;
    flex: 1;
  }

  .link-block {
    flex: 1;
    padding: 0 1rem;
  }

  .link-block.bordered {
    border-left: 1px solid var(--faded);
  }

  .link-block h3 {
    padding-top: 1rem;
    font-weight: 500;
    color: var(--white);
    margin-bottom: 1rem;
  }

  .link-block ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .link-block li {
    margin-bottom: 0.75rem;
  }

  .link-block a {
    text-decoration: none;
    font-size: 0.875rem;
    color: var(--gray);
    transition: color 0.3s;
  }

  .link-block a:hover {
    color: var(--white);
  }

  @media (max-width: 1024px) {
    .footer-container {
      flex-direction: column;
      gap: 3rem;
    }

    .links-container {
      flex-direction: column;
    }

    .link-block.bordered {
      border-left: none;
      border-top: 1px solid var(--faded);
    }
  }
</style>
