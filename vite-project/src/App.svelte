<script>
  import Button from "./assets/Button.svelte";

  let showPopup = false;
  let paymentMethod = "Bank"; // Initialize paymentMethod with a default value


  const togglePopup = () => {
    showPopup = !showPopup;
  };


</script>

<main>
  <!-- More Info Button -->
  <div class="more-info">
    <Button />
  </div>

  <!-- Grid Container -->
  <div class="grid-container">
    <!-- Left Column -->
    <div class="left-column">
      <div class="image-container">
        <img src="/deforest.jpg" alt="Deforestation Image 1" />
      </div>
      <div class="image-container">
        <img src="/deforest3.jpg" alt="Deforestation Image 3" />
      </div>
      <div class="image-container">
        <img src="/deforest5.jpg" alt="Deforestation Image 5" />
      </div>
      <div class="image-container">
        <img src="/deforest7.jpg" alt="Deforestation Image 7" />
      </div>


    </div>

    <!-- Center Image -->
    <div class="center-image">
      <img src="/preserve.jpg" alt="Rainforest Poster" />
    </div>

   <!-- Right Column -->
   <div class="right-column">

    <div class="image-container">
      <img src="/deforest2.jpg" alt="Owl Image" />
    </div>

    <div class="image-container">
      <img src="/deforest4.jpg" alt="Deforestation Image 4" />
    </div>

    <div class="image-container">
      <img src="/deforest6.jpg" alt="Deforestation Image 6" />
    </div>

    <div class="image-container">
      <img src="/deforest8.jpg" alt="Deforestation Image 8" />
    </div>
  </div>


</div>

  <!-- Donate Now Section -->
  <div class="donate-section">
    <h2>Donate Now to Protect the Rainforests!</h2>
    <p>Support our mission to save the rainforests by donating below.</p>
    <button on:click={togglePopup}>Donate Now</button>
  </div>
<!-- Donation Popup -->
{#if showPopup}
<div class="popup-overlay" on:click={togglePopup}>
  <div class="popup-content" on:click|stopPropagation>
    <h3>Donate Now</h3>

    <!-- Payment Method Selection -->
    <label for="payment-method">Choose Payment Method</label>
    <select id="payment-method" bind:value={paymentMethod}>
      <option value="Bank">Bank</option>
      <option value="PayPal">PayPal</option>
      <option value="Venmo">Venmo</option>
    </select>

    <!-- Bank Details Form -->
    {#if paymentMethod === "Bank"}
      <form>
        <label for="bank-amount">Donation Amount</label>
        <input type="number" id="bank-amount" placeholder="Enter Amount" required />

        <label for="bank-name">Full Name</label>
        <input type="text" id="bank-name" placeholder="John Doe" required />

        <label for="bank-card">Card Number</label>
        <input type="text" id="bank-card" placeholder="1234 5678 9012 3456" required />

        <label for="bank-expiry">Expiration Date</label>
        <input type="month" id="bank-expiry" required />

        <label for="bank-cvv">CVV</label>
        <input type="text" id="bank-cvv" placeholder="123" required />

        <label for="bank-zip">ZIP Code</label>
        <input type="text" id="bank-zip" placeholder="12345" required />

        <div class="button-group">
          <button type="submit" class="submit-button">Submit Donation</button>
          <button type="button" class="cancel-button" on:click={togglePopup}>Cancel</button>
        </div>
      </form>
    {/if}

    <!-- PayPal Details Form -->
    {#if paymentMethod === "PayPal"}
      <form>
        <label for="paypal-amount">Donation Amount</label>
        <input type="number" id="paypal-amount" placeholder="Enter Amount" required />

        <label for="paypal-email">PayPal Email</label>
        <input type="email" id="paypal-email" placeholder="example@example.com" required />

        <label for="paypal-card">Card Number</label>
        <input type="text" id="paypal-card" placeholder="1234 5678 9012 3456" required />

 

        <div class="button-group">
          <button type="submit" class="submit-button">Submit Donation</button>
          <button type="button" class="cancel-button" on:click={togglePopup}>Cancel</button>
        </div>
      </form>
    {/if}

    <!-- Venmo Details Form -->
    {#if paymentMethod === "Venmo"}
      <form>
        <label for="venmo-amount">Donation Amount</label>
        <input type="number" id="venmo-amount" placeholder="Enter Amount" required />

        <label for="venmo-username">Venmo Username</label>
        <input type="text" id="venmo-username" placeholder="@YourUsername" required />

        <label for="venmo-card">Card Number</label>
        <input type="text" id="venmo-card" placeholder="1234 5678 9012 3456" required />



  

        <div class="button-group">
          <button type="submit" class="submit-button">Submit Donation</button>
          <button type="button" class="cancel-button" on:click={togglePopup}>Cancel</button>
        </div>
      </form>
    {/if}
  </div>
</div>
{/if}
<!-- About Us Section -->
<div class="about-section">
  <h2>About Us</h2>

  <div class="about-container">
    <!-- Our Mission -->
    <div class="about-item">
      <h3>Our Mission</h3>
      <p>
        Our mission is to protect and preserve the world's rainforests, ensuring
        a sustainable future for our planet. We strive to combat deforestation,
        promote biodiversity, and empower communities to manage their natural
        resources responsibly.
      </p>
    </div>

    <!-- Our Impact -->
    <div class="about-item">
      <h3>Our Impact</h3>
      <p>
        Over the past decade, we've helped conserve over 1 million acres of
        rainforest and supported countless species facing extinction. Your
        donations directly contribute to these conservation efforts, leaving a
        lasting legacy for future generations.
      </p>
    </div>

    <!-- Our Goals -->
    <div class="about-item">
      <h3>Our Goals</h3>
      <p>
        We aim to expand our reach by conserving another 2 million acres of
        rainforest by 2030, implementing educational programs in local
        communities, and advocating for stronger environmental policies
        worldwide.
      </p>
    </div>
  </div>
</div>

<!-- Contact Us Section -->
<div class="contact-section">
  <h2>Contact Us</h2>

  <div class="contact-container">
    <!-- Contact Links -->
    <div class="contact-details">
      <p>
        <strong>Email:</strong>
        <a href="mailto:contact@rainforestconservation.org">contact@rainforestconservation.org</a>
      </p>
      <p>
        <strong>Phone:</strong>
        <a href="tel:+11234567890">+1 (123) 456-7890</a>
      </p>
      <p>
        <strong>Address:</strong> 45219 Cincinnati,OH
      </p>
    </div>

    <!-- Social Media Icons -->
    <div class="social-icons">
      <a href="#" target="_blank" aria-label="Facebook">
        <img src="facebook.png" alt="Facebook Icon" />
      </a>
      <a href="#" target="_blank" aria-label="Instagram">
        <img src="ins.jpg" alt="Instagram Icon" />
      </a>
      <a href="#" target="_blank" aria-label="Twitter">
        <img src="twitter.jpg" alt="Twitter Icon" />
      </a>
      <a href="#" target="_blank" aria-label="YouTube">
        <img src="youtube.jpg" alt="YouTube Icon" />
      </a>
    </div>
  </div>
</div>


</main>


<style>
  html, body {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
    overflow-x: hidden; /* Prevent horizontal scrolling */
}
main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-image: url('/path-to-your-background.jpg'); /* Replace with your actual image path */
    background-size: cover; /* Ensures the image covers the entire background */
    background-position: center; /* Centers the image */
    background-repeat: no-repeat; /* Prevents the image from repeating */
    background-attachment: fixed; /* Makes the background image fixed while scrolling */
    width: 100%;
    min-height: 100vh; /* Ensures it covers the full viewport height */
}


/* Mingjia*/
  .more-info {
    position: absolute;
    top: 20px;
    right: 20px;
  }

  .grid-container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
    gap: 20px;
    align-items: start;
  }

  .left-column,
  .right-column {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .image-container img,
  .center-image img {
    width: 100%;
    height: auto;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    object-fit: cover;
  }

  .center-image img {
    height: 100%;
  }
  .donate-section {
  margin-top: 30px;
  background: linear-gradient(to bottom, #4caf50, #81c784); /* Gradient green background */
  padding: 20px;
  border-radius: 10px;
  color: #fff; /* White text for contrast */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  text-align: center; /* Center align text */
}

.donate-section h2 {
  text-align: center;
  margin-bottom: 15px;
  color: #fff; /* White heading text */
}

.donate-section p {
  margin-bottom: 15px;
  line-height: 1.6;
  color: #f8f9fa; /* Slightly off-white for better readability */
}

.donate-section button {
  background-color: #2e7d32; /* Darker green for the button */
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  display: inline-block;
}

.donate-section button:hover {
  background-color: #1b5e20; /* Even darker green on hover */
}
.about-section {
  margin-top: 30px;
  background: linear-gradient(to bottom, #66bb6a, #a5d6a7); /* Light green gradient background */
  padding: 20px;
  border-radius: 10px;
  color: #fff; /* White text for contrast */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  text-align: left; /* Align text to the left */
}

.about-section h2 {
  text-align: center;
  margin-bottom: 20px;
  color: #fff; /* White heading text */
}

.about-container {
  display: flex;
  flex-direction: column;
  gap: 20px; /* Space between sub-containers */
}

.about-item {
  background: #ffffff; /* Pure white background for sub-sections */
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.about-item h3 {
  margin-bottom: 10px;
  font-size: 1.5em;
  color: #4caf50; /* Green text for headings */
}

.about-item p {
  font-size: 1em;
  line-height: 1.6;
  color: #333; /* Dark text for readability */
}


  .popup-content {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    z-index: 11;
    width: 90%;
    max-width: 500px;
  }

  .popup-content h3 {
    margin-bottom: 20px;
    color: #333;
  }

  .popup-content label {
    display: block;
    margin-top: 10px;
    text-align: left;
    color: #333;
  }

  .popup-content input,
  .popup-content select {
    width: calc(100% - 20px);
    padding: 10px;
    margin: 5px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
  }

  .button-group {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
  }

  .button-group button {
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
  }

  .submit-button {
    background-color: #4caf50;
    color: white;
  }

  .cancel-button {
    background-color: #ccc;
    color: #333;
  }

  .cancel-button:hover {
    background-color: #aaa;
  }

  .submit-button:hover {
    background-color: #45a049;
  }


  .contact-section {
  margin-top: 30px;
  background: linear-gradient(to bottom, #66bb6a, #a5d6a7); /* Light green gradient background */
  padding: 20px;
  border-radius: 10px;
  color: #fff; /* White text for contrast */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.contact-section h2 {
  margin-bottom: 20px;
  color: #fff;
}

.contact-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.contact-details p {
  font-size: 1.2em;
  margin: 5px 0;
  color: #fff;
}

.contact-details a {
  color: #ffeb3b; /* Bright yellow for links */
  text-decoration: none;
}

.contact-details a:hover {
  text-decoration: underline;
}

.social-icons {
  display: flex;
  gap: 15px;
  justify-content: center;
}

.social-icons a {
  display: inline-block;
  width: 40px;
  height: 40px;
}

.social-icons img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

</style>