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
  padding: 1rem;
  margin-top: 8rem;
  font-family: 'Inter', sans-serif;
  color: var(--gray);
}

.footer-container {
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  align-items: flex-start;
  justify-content: space-between;
}

.logo {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.25rem;
  justify-content: flex-start;
  width: 100%;
  max-width: 200px;
  margin: 0 auto;
  text-align: center;
}

.logoimg {
  height: 60px;
  width: 40px;
}

.logo span {
  font-size: 1.25rem;
  font-weight: bold;
  color: var(--white);
}

.links-container {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  flex: 1;
  justify-content: space-between;
  width: 100%;
}

.link-block {
  min-width: 140px;
  flex: 1 1 160px;
  padding: 0;
}

.link-block h3 {
  font-weight: 500;
  color: var(--white);
  margin-bottom: 0.75rem;
  font-size: 1rem;
}

.link-block ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.link-block li {
  margin-bottom: 0.5rem;
}

.link-block a {
  text-decoration: none;
  font-size: 0.85rem;
  color: var(--gray);
  transition: color 0.3s;
}

.link-block a:hover {
  color: var(--white);
}

/* Responsive tweaks */
@media (max-width: 768px) {
  .footer-container {
    flex-direction: column;
    gap: 1.5rem;
    align-items: center;
    text-align: center;
  }

  .links-container {
    justify-content: center;
  }

  .link-block {
    flex: 1 1 45%;
    min-width: 140px;
  }

  .logo {
    align-items: center;
    margin: 0 auto;
  }
}

@media (max-width: 480px) {
  .link-block {
    flex: 1 1 100%;
  }

  .logo {
    width: 100%;
  }
}

</style>
