<script lang="ts">
    export let data: { title: string; description: string }[][] = [[]]; // 2D array
  </script>
  
  <style>
    .grid-container {
      display: flex;
      flex-direction: column;
      max-width: 80vw;
      width: 80%;
      height: auto;
      padding: 20px;
      background: black; /* Matches your background */
    }
  
    .grid-row {
      display: flex;
      flex-wrap: nowrap;
    }
  
    .grid-cell {
      flex: 1;
      padding: 1rem;
      text-align: center;
      color: var(--white);
      border-right: 1px solid var(--grayfaded);
      border-bottom: 1px solid var(--grayfaded);
    }
  
    /* Remove right border for last cell in each row */
    .grid-cell:last-child {
      border-right: none;
    }
  
    /* Remove bottom border for cells in last row */
    .grid-row:last-child .grid-cell {
      border-bottom: none;
    }
  
    h3 {
      margin: 0 0 0.5rem 0;
      font-size: 1.2rem;
      color: var(--white);
    }
  
    p {
      margin: 0;
      color: var(--gray);
    }
  
    @media (max-width:768px){
        .grid-container {
        max-width: 100vw;
        width: 100%;
      }
    }

    @media (max-width: 568px) {
 
  .grid-container{
    padding-left: 100px;
    padding-right: 100px;
    margin-bottom: 100px;
  }

      .grid-row {
        flex-direction: column;
      }
  
      .grid-row:last-child .grid-cell {
        border-bottom: 1px solid var(--grayfaded);
        border-left: 1px solid var(--grayfaded);
    }

      .grid-cell {
        border-right: none;
        margin-bottom: 1rem;

      }
    }
  </style>
  
  <div class="grid-container">
    {#each data as row, i}
      <div class="grid-row">
        {#each row as cell, j}
          <div class="grid-cell">
            <h3>{cell.title}</h3>
            <p>{cell.description}</p>
          </div>
        {/each}
      </div>
    {/each}
  </div>
  