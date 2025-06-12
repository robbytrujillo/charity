<script>
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
</script>

<style>
  .xs-input-group {
    margin-bottom: 20px;
  }

  .xs-checkbox-wrapper label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 15px;
    font-weight: 500;
    color: #002147;
    margin-bottom: 20px;
  }

  .xs-checkbox-wrapper input[type="checkbox"] {
    width: 18px;
    height: 18px;
    margin: 0;
    accent-color: #ff4e4e;
  }

  button.btn-warning {
    background-color: #ff4e4e;
    color: #fff;
    font-weight: bold;
    padding: 10px 30px;
    border-radius: 30px;
    border: none;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  button.btn-warning .fa-heart {
    color: white;
  }

  .xs-banner-inner-section {
    background-size: cover;
    background-position: center;
    padding: 80px 0;
    position: relative;
  }

  .xs-black-overlay {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(0,0,0,0.4);
  }

  .xs-inner-banner-content {
    position: relative;
    z-index: 1;
    text-align: center;
  }

  .color-white {
    color: white;
  }

  .xs-donation-form-images img {
    width: 100%;
    border-radius: 10px;
  }

  .bg-gray {
    background-color: #f9f9f9;
  }

  .xs-section-padding {
    padding: 60px 0;
  }

  .xs-title {
    font-size: 28px;
    font-weight: bold;
    margin-bottom: 10px;
    color: #0d1b4c;
  }

  .color-green {
    color: #1abc9c;
  }

  .color-light-red {
    color: #ff4e4e;
  }
</style>

<Header />

<!-- Banner -->
<section class="xs-banner-inner-section parallax-window" style="background-image:url('/assets/images/about-bg.jpg')">
  <div class="xs-black-overlay"></div>
  <div class="container">
    <div class="color-white xs-inner-banner-content">
      <h2>Donate Now</h2>
      <p>Give a helping hand for poor people</p>
      <ul class="xs-breadcumb">
        <li class="badge badge-pill badge-primary">
          <a href="/" class="color-white">Home /</a> Donate
        </li>
      </ul>
    </div>
  </div>
</section>

<main class="xs-main">
  <!-- Donation Form -->
  <section class="xs-section-padding bg-gray">
    <div class="container">
      <div class="row">
        <!-- Image -->
        <div class="col-lg-6 mb-4 mb-lg-0">
          <div class="xs-donation-form-images">
            <img src="/assets/images/family-gaza.jpg" alt="Family Image" />
          </div>
        </div>
        <!-- Form -->
        <div class="col-lg-6">
          <div class="xs-donation-form-wraper">
            <div class="xs-heading xs-mb-30">
              <h2 class="xs-title">Make a donation</h2>
              <p class="small">
                To learn more about make donate charity with us visit our
                <span class="color-green">"Contact us"</span> site.
                By calling <span class="color-green">+44(0) 800 883 8450</span>.
              </p>
              <span class="xs-separetor v2"></span>
            </div>

            <form action="#" method="post" id="xs-donation-form" class="xs-donation-form">
              <div class="xs-input-group">
                <label for="xs-donate-amount">Donation Amount <span class="color-light-red">**</span></label>
                <input type="number" id="xs-donate-amount" class="form-control" placeholder="Minimum of $5" required>
              </div>

              <div class="xs-input-group">
                <label for="xs-donate-name">Your name <span class="color-light-red">**</span></label>
                <input type="text" id="xs-donate-name" class="form-control" placeholder="Your Awesome Name" required>
              </div>

              <div class="xs-input-group">
                <label for="xs-donate-email">Your Email <span class="color-light-red">**</span></label>
                <input type="email" id="xs-donate-email" class="form-control" placeholder="email@charity.com" required>
              </div>

              <div class="xs-input-group xs-checkbox-wrapper">
                <label>
                  <input type="checkbox" id="xs-donate-agree" required />
                  I Agree <span class="color-light-red">**</span>
                </label>
              </div>

              <button type="submit" class="btn btn-warning">
                <i class="fa fa-heart"></i> Donate Now
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</main>

<Footer />
