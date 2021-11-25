<template>
<div>
    <Topbar />
    <div class='container-fluid'>
        <div class='row'>
            <div class='col-sm-12 col-md-3 col-lg-3'></div>
            <div class='col-sm-12 col-md-6 col-lg-6 bg-dark'>
                <div v-if='!results' class='h-full d-flex align-items-center justify-content-center'>
                    <img src='~/assets/img/load.gif' class='img-load'>
                </div>
                <div v-if='results' class='h-full'>
                    <div class='mt-5 pt-5 pb-5 mb-5'>
                        <div class="card border-secondary bg-transparent mb-5">
                            <div class="card-header d-flex justify-content-between align-items-center text-white border-bottom border-secondary">
                                <div class='w-setengah border-end border-secondary'>
                                    Top Female Character
                                </div>
                                <div>
                                    {{ results.tanggal }}
                                </div>
                            </div>
                            <div class="card-body border-top border-secondary text-white d-flex justify-content-around align-items-center">
                                <div class='d-flex align-items-center'>
                                    <img src='https://anitrendz.net/regular/main/images/icons/up-arrow.png' class='icon'>
                                    <small class='-mt-2px'><small>&nbsp;Naik</small></small>
                                </div>
                                <div class='d-flex align-items-center'>
                                    <img src='https://anitrendz.net/regular/main/images/icons/down-arrow.png' class='icon'>
                                    <small class='-mt-2px'><small>&nbsp;Turun</small></small>
                                </div>
                                <div class='d-flex align-items-center'>
                                    <img src='https://anitrendz.net/regular/main/images/icons/right-arrow.png' class='icon'>
                                    <small class='-mt-2px'><small>&nbsp;Tidak berubah</small></small>
                                </div>
                            </div>
                            <div class="card-body text-white d-flex justify-content-around align-items-center">
                                <div class='d-flex align-items-center justify-content-center'>
                                    <img src='https://anitrendz.net/regular/main/images/icons/new.png' class='icon'>
                                    <small class='-mt-2px'><small>&nbsp;Baru</small></small>
                                </div>
                                <div class='d-flex align-items-center'>
                                    <img src='https://anitrendz.net/regular/main/images/icons/re-entry.png' class='icon'>
                                    <small class='-mt-2px'><small>&nbsp;Re-entry</small></small>
                                </div>
                                <div class='d-flex align-items-center'>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
                                    </svg>
                                    <small class='-mt-2px'><small>&nbsp;Posisi tertinggi</small></small>
                                </div>
                            </div>
                            <div class="card-body text-white d-flex justify-content-around align-items-center">
                                <div class='d-flex align-items-center'>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12.066 11.2a1 1 0 000 1.6l5.334 4A1 1 0 0019 16V8a1 1 0 00-1.6-.8l-5.333 4zM4.066 11.2a1 1 0 000 1.6l5.334 4A1 1 0 0011 16V8a1 1 0 00-1.6-.8l-5.334 4z" />
                                    </svg>
                                    <small class='-mt-2px'><small>&nbsp;Posisi sebelumnya</small></small>
                                </div>
                                <div class='d-flex align-items-center justify-content-center'>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                                    </svg>
                                    <small class='-mt-2px'><small>&nbsp;Minggu lalu top 10</small></small>
                                </div>
                            </div>
                        </div>
                        <div v-for='h in results.data' class='mb-3'>
                            <div class='text-white d-flex border border-bottom-0 border-secondary rounded-top'>
                                <div class='d-flex align-items-center border border-end border-secondary px-3'>
                                    <h4>{{ h.rankChar.length <= 1 ? "0" + h.rankChar : h.rankChar }}</h4>
                                </div>
                                <div class='d-flex align-items-center border border-secondary'>
                                    <img :src='h.thumbChar' class='thumb-char'>
                                </div>
                                <div class='w-full'>
                                    <div class='h-setengah px-3 border-bottom border-secondary d-flex align-items-center'>
                                        <b>{{ h.namaChar }}</b>
                                    </div>
                                    <div class='h-setengah px-3 border-top border-secondary py-3 d-flex align-items-center'>
                                        <small class='my-2'><small>{{ h.judulAnime }}</small></small>
                                    </div>
                                </div>
                            </div>
                            <div class='text-white w-full border-secondary py-1 border rounded-bottom d-flex justify-content-around align-items-center'>
                                <div>
                                    <div class='d-flex justify-content-center align-items-center'>
                                        <img :src='h.status.arrow' class='icon'>
                                    </div>
                                </div>
                                <div>
                                    <b>{{ h.status.numberStats }}</b>
                                </div>
                                <div>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
                                    </svg>
                                    <b> {{ h.status.peakStats }}</b>
                                </div>
                                <div>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12.066 11.2a1 1 0 000 1.6l5.334 4A1 1 0 0019 16V8a1 1 0 00-1.6-.8l-5.333 4zM4.066 11.2a1 1 0 000 1.6l5.334 4A1 1 0 0011 16V8a1 1 0 00-1.6-.8l-5.334 4z" />
                                    </svg>
                                    <b> {{ h.status.prevStats }}</b>
                                </div>
                                <div>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                                    </svg>
                                    <b>{{ h.status.weekStats == '' ? '-' : h.status.weekStats }}</b>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class='col-sm-12 col-md-3 col-lg-3'></div>
        </div>
    </div>
    <Botbar />
</div>
</template>

<script>
export default {
    data() {
        return {
            results: null
        }
    },

    mounted() {
        this.$axios.get('https://limitless-sea-61725.herokuapp.com/https://coba-nuxt-ssr-ricko-v.vercel.app/api/anitrendz/femalerank')
            .then(res => {
                this.results = res.data;
            })
            .catch(err => {
                alert(err);
            })
    }
}
</script>
