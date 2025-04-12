<script>
    let isOpen = false;
    import {Button } from '$lib/index'
      import Logo from "$lib/assets/logo.svg"

  </script>
  
  <style>
    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 70px;
      padding: 0 1.5rem;
      background-color: var(--accent);
      color: white;
      position: relative;
      z-index: 10;
    }
  
    .navbar-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex: 1;
      max-width: 1200px;
      margin: 0 auto;
      width: 100%;
    }
  
    .logo span{
      font-size: 1.5rem;
      font-weight: bold;
    }
  
    .logo{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .menu {
      display: none;
      flex-direction: column;
      position: absolute;
      top: 70px;
      left: 0;
      right: 0;
      background: var(--accent);
      padding: 1rem 0;
      text-align: center;
      transition: all 0.3s ease;
    }
  
    .menu a {
      padding: 0.5rem 0;
      text-decoration: none;
      color: white;
      font-weight: 500;
    }
  
    .menu.show {
      display: flex;
    }
  
    .hamburger {
      cursor: pointer;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      width: 25px;
      height: 18px;
    }
  
    .bar {
      height: 3px;
      background: var(--gray);
      transition: all 0.3s ease;
      border-radius: 2px;
    }
  
    .open .bar1 {
      transform: rotate(45deg) translate(5px, 5px);
    }
  
    .open .bar2 {
      opacity: 0;
    }
  
    .open .bar3 {
      transform: rotate(-45deg) translate(5px, -5px);
    }
  
    .nav-btn{
        display: none;
    }
  
.logoimg{
    height: 80px;
    width: 50px;
}

    @media (min-width: 768px) {
      .hamburger {
        display: none;
      }
      .nav-btn{
        display: block;
      }

      nav{
        background-color: transparent;
      }
      .menu {
        display: flex;
        position: static;
        flex-direction: row;
        background: none;
        padding: 0;
        height: auto;
        align-items: center;
        justify-content: center;
        gap: 2rem;
      }
  
      .menu.show {
        display: flex;
      }
  
      .nav-btn {
        margin-top: 12px;
      }
  
      .navbar-container {
        display: grid;
        grid-template-columns: 1fr auto 1fr;
      }
  
      .left {
        justify-self: start;
      }
  
      .center {
        justify-self: center;
      }
  
      .right {
        justify-self: end;
      }
    }
  </style>
  
  <nav>
    <div class="navbar-container">
      <div class="left logo">
        <img class="logoimg" src={Logo} alt="logo">
       <span>Magnimont</span>
    </div>
  
      <div class="center menu {isOpen ? 'show' : ''}">
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/services">Services</a>
        <a href="/contact">Contact</a>
      </div>
  
      <div class="right">
        <div class="nav-btn">

            <Button height='42px'/>
        </div>
      </div>
    </div>
  
    <div class="hamburger {isOpen ? 'open' : ''}" on:click={() => (isOpen = !isOpen)}>
      <span class="bar bar1"></span>
      <span class="bar bar2"></span>
      <span class="bar bar3"></span>
    </div>
  </nav>
  