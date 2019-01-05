<template>
    <div id="footer">
      <footer>
        <div class="container">
          <ul class="category">
            <h3>Category</h3>
            <li><a href="#">Home</a></li>
            <li><a href="#">About us</a></li>
            <li><a href="#">Eshop</a></li>
            <li><a href="#">Features</a></li>
            <li><a href="#">New collections</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Contact</a></li>
          </ul>

          <ul class="account">
            <h3>Our Account</h3>
            <li><a href="">Your Account</a></li>
            <li><a href="">Personal information</a></li>
            <li><a href="">Addresses</a></li>
            <li><a href="">Discount</a></li>
            <li><a href="">Orders history</a></li>
            <li><a href="">Addresses</a></li>
            <li><a href="">Search Terms</a></li>
          </ul>

          <ul class="support">
            <h3>Our Support</h3>
            <li><a href="">Site Map</a></li>
            <li><a href="">Search Terms</a></li>
            <li><a href="">Advanced Search</a></li>
            <li><a href="">Mobile</a></li>
            <li><a href="">Contact Us</a></li>
            <li><a href="">Mobile</a></li>
            <li><a href="">Addresses</a></li>
          </ul>

          <ul class="newsletter">
            <h3>Newsletter</h3>
            <p>Join thousands of other people subscribe to our news</p>

            <form>
                <input type="text" name="email" placeholder="INSERT EMAIL">
                <input type="submit" value="SUBMIT">
            </form>

            <div class="payments">
              <img src="../assets/images/aex.png" alt="American Express">
              <img src="../assets/images/mastercard.png" alt="MasterCard">
              <img src="../assets/images/maestero.png" alt="Maestero">
              <img src="../assets/images/paypal.png" alt="PayPal">
              <img src="../assets/images/visa_straight.png" alt="Visa">
            </div>
          </ul>

          <ul class="about">
            <h3>About us</h3>
            <p>Our vision while creating Surfhouse was to deliver a surf-inspired boutique hotel which combines all of our favorite things: the beach lifestyle and local surf community, good vibes, traveling, and stewardship of our town.  </p>
            
            <div class="contact-us">
              <li>Phone: <a href="#">1-999-342-9876</a></li>
              <li>E-mail: <a href="#"><span class="email-color">info@surfhouse.com</span></a></li>
            </div>
          </ul>
        </div>
      </footer>
      
      <div class="copyright">
        <div class="container">
          <p><span>&#9400;</span> 2018 SURFHOUSE</p>
        </div>
      </div>
    </div>
</template>

<script>
  export default {
    name: 'MainFooter'
  }
</script>