<script>
    import Modal from "./Modal.svelte";

    export let charities;

    let isModalOpen = false;

    function calculateFunded(pledged, target) {
        return Math.round((1 / (target / pledged)) * 100)
    }

    function formatCurrency(nominal) {
        return nominal.toLocaleString('id-ID', { 
            style: 'currency', 
            currency: 'IDR' 
        })
    }

    function calculateDaysRemaining(date_end) {
        const delta = date_end - new Date();

        const oneDay = 24 * 60 * 60 * 1000;

        return Math.round(Math.abs(delta / oneDay));
    }

    function handleButton() {
        // console.log('Button click')
        isModalOpen = true;
    }

    function handleCloseModal() {
        isModalOpen = false;
    }
</script>

<style>
    .xs-list-with-content {
        font-size: 8px;
    }

    /* .number-percentage-count number-percentage {
        font-size: 8px;
    } */

    .show {
        display: block;
        background-color: rgba (0, 0, 0, 0.45);
    }
</style>

<!-- popularCauses section -->
<section id="popularcause" class="bg-gray waypoint-tigger xs-section-padding">
    <div class="container">
        <div class="xs-heading row xs-mb-60">
            <div class="col-md-9 col-xl-9">
                <h2 class="xs-title">Popular Causes</h2>
                <span class="xs-separetor dashed"></span>
                <p>Funding Charity has built a platform focused on aiding entrepreneurs, startups, and <br> companies
                    raise capital from anyone.</p>
            </div><!-- .xs-heading-title END -->
        </div><!-- .row end -->

        {#if charities !== undefined}
            {#each charities as charity}
                <div class="row">
                    <div class="col-lg-4 col-md-6">
                        <!-- modal goes here -->
                        <!-- Modal -->
                         {#if isModalOpen === true}
                        <Modal>
                            <!-- <h1>Ini adalah Modal</h1> -->

                            <div class="modal fade show" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel">
                                <div class="modal-dialog" role="document">
                                    <div class="modal-content">
                                        <div class="modal-header">
                                            <h5 class="modal-title" id="exampleModalLabel">{charity.title}</h5>
                                            <button type="button" class="close" data-dismiss="modal" aria-label="Close" on:click={handleCloseModal}>
                                            <span aria-hidden="true">&times;</span>
                                            </button>
                                        </div>
                                        <div class="modal-body">
                                            <form>
                                                <div class="form-group">
                                                    <label for="exampleInputAmount">Amount donation</label>
                                                    <input required type="number" class="form-control" id="exampleInputAmount"aria-describedby="amountHelp" placeholder="Enter amount">
                                                </div>
                                                <div class="form-group">
                                                    <label for="exampleInputName">Your name</label>
                                                    <input required type="text" class="form-control" id="exampleInputName"aria-describedby="nameHelp" placeholder="Enter full name">
                                                </div>
                                                <div class="form-group">
                                                    <label for="exampleInputEmail1">Email address</label>
                                                    <input required type="email" class="form-control" id="exampleInputEmail1"aria-describedby="emailHelp" placeholder="Enter email">
                                                </div>
                                                <div class="form-check">
                                                    <input type="checkbox" class="form-check-input" id="exampleCheck1">
                                                    <label class="form-check-label" for="exampleCheck1">I Agree</label>
                                                </div>
                                            </form>
                                        </div>
                                        <div class="modal-footer">
                                            <button type="button" class="btn btn-primary">Continue</button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </Modal>
                        {/if}
                        
                        <div class="xs-popular-item xs-box-shadow">
                            <div class="xs-item-header">

                                <img src="{charity.thumbnail}" alt="">

                                <div class="xs-skill-bar">
                                    <div class="xs-skill-track">
                                        <p><span class="number-percentage-count number-percentage" data-value="90"
                                                data-animation-duration="3500">{calculateFunded(charity.pledged, charity.target)}</span>%</p>
                                    </div>
                                </div>
                            </div><!-- .xs-item-header END -->
                            <div class="xs-item-content">
                                <ul class="xs-simple-tag xs-mb-20">
                                    <li><a href="">{charity.category}</a></li>
                                </ul>

                                <a href="#" class="xs-post-title xs-mb-30">{charity.title}</a>

                                <ul class="xs-list-with-content">
                                    <li>{formatCurrency(charity.pledged)}<span>Pledged</span></li>
                                    <li><span class="number-percentage-count number-percentage" data-value="90"
                                            data-animation-duration="3500">{calculateFunded(charity.pledged, charity.target)}</span>% <span>Funded</span></li>
                                    <li>{calculateDaysRemaining(charity.date_end)}<span>Days to go</span></li>
                                </ul>

                                <span class="xs-separetor"></span>

                                <div class="row xs-margin-0">
                                    <div class="xs-round-avatar">
                                        <img src="{charity.profile_photo}" alt="">
                                    </div>
                                    <div class="xs-avatar-title">
                                        <a href="#"><span>By</span>{charity.profile_name}</a>
                                    </div>
                                </div>

                                <span class="xs-separetor"></span>

                                <button on:click={handleButton} data-toggle="modal" data-target="#exampleModal"
                                    class="btn btn-primary btn-block">
                                    Donate This Cause
                                </button>
                            </div><!-- .xs-item-content END -->
                        </div><!-- .xs-popular-item END -->
                    </div>
                </div><!-- .row end -->
            {/each}
        {/if}
    </div><!-- .container end -->
</section><!-- End popularCauses section -->


<!-- <div>
    <h2>Daftar Charity</h2>
    {#if charities !== undefined}
        <ul>
            {#each charities as charity}
            <li>{charity.title} - {charity.category}</li>
            {/each}
        </ul>
    {:else}
        <h5>Data belum tersedia</h5>
    {/if}
</div> -->