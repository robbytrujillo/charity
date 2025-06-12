<script>
    import Header from "../components/Header.svelte";
    import Footer from "../components/Footer.svelte";
</script>

<style>
    #xs-input-checkbox {
        display: flex;
        align-items: center;;
    }

    #xs-donate-agree {
        /* margin-left: 10px; */
        width: 35px;
    }

    label[for="xs-donate-agree"] {
        margin: 0;
    }

    .xs-checkbox-wrapper {
    margin-top: 20px;
    }

    .xs-checkbox-wrapper label {
    display: flex;
    align-items: center;
    gap: 10px; /* Jarak antara checkbox dan tulisan */
    margin-bottom: 20px;
    }

    .xs-checkbox-wrapper input[type="checkbox"] {
        width: 18px;
        height: 18px;
    }
    
    .checkbox-label {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 16px;
    font-weight: 500;
    color: #002147; /* atau warna teks kamu */
    }

    .checkbox-label input[type="checkbox"] {
    width: 18px;
    height: 18px;
    margin: 0;
    }
</style>

<Header />

<!-- welcome section -->
	<!--breadcumb start here-->
	<section class="xs-banner-inner-section parallax-window" style="background-image:url('/assets/images/about-bg.jpg')">
        <div class="xs-black-overlay"></div>
        <div class="container">
            <div class="color-white xs-inner-banner-content">
                <h2>Donate Now</h2>
                <p>Give a helping hand for poor people</p>
                <ul class="xs-breadcumb">
                    <li class="badge badge-pill badge-primary">
                        <a href="index.html" class="color-white">Home /</a> Donate
                    </li>
                </ul>
            </div>
        </div>
	</section><!--breadcumb end here--><!-- End welcome section -->
	<main class="xs-main">
	<!-- donation form section -->
	<section class="xs-section-padding bg-gray">
        <div class="container">
            <div class="row">
                <div class="col-lg-6">
                    <div class="xs-donation-form-images"><img src=
                    "/assets/images/family-gaza.jpg" class="img-responsive" alt="Family Images"></div>
                </div>
                <div class="col-lg-6">
                    <div class="xs-donation-form-wraper">
                        <div class="xs-heading xs-mb-30">
                            <h2 class="xs-title">Make a donation</h2>
                            <p class="small">To learn more about make donate charity
                                with us visit our "<span class="color-green">Contact
                                us</span>" site. By calling <span class=
                                "color-green">+44(0) 800 883 8450</span>.</p><span class=
                                "xs-separetor v2"></span>
                        </div><!-- .xs-heading end -->

                        <form action="#" method="post" id="xs-donation-form" class="xs-donation-form" name="xs-donation-form">
                            <div class="xs-input-group">
                            <label for="xs-donate-name">Donation Amount <span class=
                            "color-light-red">**</span></label> <input type="text"
                            name="name" id="xs-donate-name" class="form-control"
                            placeholder="Minimum of $5">
                            </div><!-- .xs-input-group END -->
                            <div class="xs-input-group">
                                <label for="xs-donate-name">Your name 
                                    <span class=color-light-red>**</span>
                                </label>
                                <input type="text" name="name" id="xs-donate-name" class="form-control" placeholder="Your Awesome Name">
                            </div>
                            <div class="xs-input-group">
                                <label for="xs-donate-email">Your Email 
                                    <span class=color-light-red>**</span>
                                </label>
                                <input type="email" name="email" id="xs-donate-email" class="form-control" placeholder="email@charity.com">
                            </div>
                            <div class="xs-input-group xs-checkbox-wrapper" id="xs-input-checkbox">
                                <label for="xs-donate-agree">
                                     <input type="checkbox" name="agree" id="xs-donate-agree">
                                    I Agree
                                    <span class="color-light-red">**</span>
                                </label>
                            </div>
                            <button type="submit" class="btn btn-warning"><span class=
                            "badge"><i class="fa fa-heart"></i></span> Donate
                            now</button>
                        </form><!-- .xs-donation-form #xs-donation-form END -->
                    </div>
                </div>
            </div><!-- .row end -->
        </div><!-- .container end -->
	</section><!-- End donation form section -->
	</main><!-- footer section start -->

    <Footer />