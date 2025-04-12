<script lang="ts">
  import { onMount } from 'svelte';
  export let items: { image: string; quote: string; name: string }[] = [];
  export let direction: 'left' | 'right' = 'left';
  export let speed: 'fast' | 'normal' | 'slow' = 'fast';
  export let pauseOnHover: boolean = true;
  export let className: string = '';

  let containerRef: HTMLDivElement;
  let scrollerRef: HTMLUListElement;
  let animationStarted = false;

  const getDuration = () => {
    switch (speed) {
      case 'fast': return '20s';
      case 'normal': return '40s';
      case 'slow': return '80s';
    }
  };

  const setupScroller = () => {
    if (scrollerRef && items.length > 0) {
      const children = Array.from(scrollerRef.children);
      children.forEach((child) => {
        scrollerRef.appendChild(child.cloneNode(true));
      });
      animationStarted = true;
    }
  };

  onMount(() => {
    setupScroller();
  });
</script>

<style>
  * {
    font-family: abc;
  }

  .container {
    margin-bottom: 6rem;
    position: relative;
    z-index: 20;
    max-width: 100%;
    overflow: hidden;
    mask-image: linear-gradient(to right, transparent, white 20%, white 80%, transparent);
    -webkit-mask-image: linear-gradient(to right, transparent, white 20%, white 80%, transparent);
  }

  .scroller {
    display: flex;
    gap: 1rem;
    width: max-content;
    flex-wrap: nowrap;
    animation: scroll var(--animation-duration) linear infinite;
    animation-direction: var(--animation-direction);
  }

  .pause:hover {
    animation-play-state: paused;
  }

  @keyframes scroll {
    0% { transform: translateX(0); }
    100% { transform: translateX(-50%); }
  }

  li {
    position: relative;
    overflow: hidden;
    width: 350px;
    max-width: 100%;
    padding: 20px;
    background: var(--black);
    border: 1px solid var(--grayfaded);
    transition: background 0.3s ease-in-out;
    flex-shrink: 0;
  }

  li:hover {
    background-color: var(--faded);
  }

  blockquote {
    width: 100%;
    border-radius: 16px;
    padding: 16px;
    color: var(--white);
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  h1 {
    margin-top: 0;
    font-size: 1.2rem;
    color: var(--white);
  }

  p.quote {
    margin-top: 1rem;
    font-size: 1rem;
    color: var(--gray);
  }
</style>

<div
  bind:this={containerRef}
  class="container {className}"
  style="--animation-duration: {getDuration()}; --animation-direction: {direction === 'left' ? 'forwards' : 'reverse'}"
>
  <ul
    bind:this={scrollerRef}
    class="scroller {pauseOnHover ? 'pause' : ''}"
  >
    {#each [...items, ...items] as item (item.name + Math.random())}
      <li>
        <blockquote>
          <div class="flex flex-row items-center gap-3 mt-4">
            <img src={item.image} alt={item.name} class="w-10 h-10 rounded-full" />
            <h1>{item.name}</h1>
          </div>
          <p class="quote">{item.quote}</p>
        </blockquote>
      </li>
    {/each}
  </ul>
</div>
