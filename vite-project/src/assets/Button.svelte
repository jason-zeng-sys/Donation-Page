<script>
    export let text = "More Info ";
    export let url = "https://www.nature.org/en-us/what-we-do/our-priorities/protect-water-and-land/land-and-water-stories/how-we-conserve-forests/";
    export let color = "#007bff";
    export let hoverColor = "#0056b3";
  
    const handleClick = () => {
      window.open(url, "_blank");
    };
  </script>
  
  <button
    class="custom-button"
    style="background-color: {color};"
    on:click={handleClick}
  >
    {text}
  </button>
  
  <style>
    .custom-button {
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      transition: background-color 0.3s ease;
    }
  
    .custom-button:hover {
      background-color: var(--hoverColor, #0056b3);
    }
  </style>
  