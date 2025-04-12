<script lang="ts">
    
      import Logo from "$lib/assets/logo.svg"
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
  

<style>
     .logo span{
      font-size: 1.5rem;
      font-weight: bold;
    }
  footer{
    margin-top: 100px;
  }
    .logo{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .logoimg{
    height: 80px;
    width: 50px;
}
</style>

  <footer class="bg-black text-zinc-500 py-16 px-6 font-[Inter]">
    <div class="max-w-7xl mx-auto flex flex-col lg:flex-row lg:space-x-16">
      <!-- Status Section -->
      <div class="mb-16 lg:mb-0 lg:w-1/3 space-y-6">
        <div class="inline-flex items-center space-x-2  px-4 py-2 w-fit">
            <div class="left logo">
                <img class="logoimg" src={Logo} alt="logo">
               <span>Magnimont</span>
            </div>
        </div>
      </div>
  
      <!-- Footer Links -->
      <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-x-8 gap-y-12 lg:flex-1">
        {#each Object.entries(footerLinks) as [category, links]}
          <div class="space-y-4">
            <h3 class="text-white font-medium">{category}</h3>
            <ul class="space-y-3">
              {#each links as link}
                <li>
                  <a
                    href={link.href}
                    class="text-sm hover:text-zinc-300 transition-colors"
                  >
                    {link.name}
                  </a>
                </li>
              {/each}
            </ul>
          </div>
        {/each}
      </div>
    </div>
  </footer>
  