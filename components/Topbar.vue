<template>
<div class='container-fluid position-fixed fixed-top'>
    <div class='row'>
        <div class='col-sm-12 col-md-3 col-lg-3'></div>
        <div class='col-sm-12 col-md-6 col-lg-6 bg-dark text-white px-3 border-bottom border-secondary'>
            <ul class="nav justify-content-between py-2">
                <li class="nav-item align-items-center d-flex">
                    <h4><b>Animetrend</b></h4>
                </li>
                <li class="nav-item">
                    <button @click='redirect("/tentang")' v-bind:class="[this.$route.path == '/tentang' ? 'text-white' : 'botbar']" class='bg-transparent shadow-none text-secondary border-0'>
                        <svg xmlns="http://www.w3.org/2000/svg" class="icon-theme" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                        </svg>
                    </button>
                </li>
            </ul>
        </div>
        <div class='col-sm-12 col-md-3 col-lg-3'></div>
    </div>
</div>
</template>

<script>
export default {
    methods: {
        redirect(q) {
            this.$router.push({
                path: q
            })
        }
    }
}
</script>

<style>
.icon-theme {
    width: 1.5rem;
    height: 1.5rem;
}
</style>
