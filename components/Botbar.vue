<template>
<div class='container-fluid position-fixed fixed-bottom'>
    <div class='row'>
        <div class='col-sm-12 col-md-3 col-lg-3'></div>
        <div class='col-sm-12 col-md-6 col-lg-6 bg-dark border-top border-secondary'>
            <ul class="nav justify-content-around py-2">
                <li class="nav-item">
                    <button @click='redirect("/")' v-bind:class="[aktif == '/' ? '' : 'botbar']" class='text-secondary shadow-none border-0 bg-transparent'>
                        <img src='~/assets/img/topanime.png' class='img-botbar'>
                        <br>
                        <small v-bind:class="[aktif == '/' ? 'text-white' : '']">Anime</small>
                    </button>
                </li>
                <li class="nav-item">
                    <button @click='redirect("/male")' v-bind:class="[aktif == '/male' ? '' : 'botbar']" class='text-secondary shadow-none border-0 bg-transparent'>
                        <img src='~/assets/img/male.png' class='img-botbar'>
                        <br>
                        <small v-bind:class="[aktif == '/male' ? 'text-white' : '']">Male</small>
                    </button>
                </li>
                <li class="nav-item">
                    <button @click='redirect("/female")' v-bind:class="[aktif == '/female' ? '' : 'botbar']" class='text-secondary shadow-none border-0 bg-transparent'>
                        <img src='~/assets/img/girl.png' class='img-botbar'>
                        <br>
                        <small v-bind:class="[aktif == '/female' ? 'text-white' : '']">Female</small>
                    </button>
                </li>
                <li class="nav-item">
                    <button @click='redirect("/couple")' v-bind:class="[aktif == '/couple' ? '' : 'botbar']" class='text-secondary shadow-none border-0 bg-transparent'>
                        <img src='~/assets/img/couple.png' class='img-botbar'>
                        <br>
                        <small v-bind:class="[aktif == '/couple' ? 'text-white' : '']">Couple</small>
                    </button>
                </li>
                <li class="nav-item">
                    <button @click='redirect("/op")' v-bind:class="[aktif == '/op' ? '' : 'botbar']" class='text-secondary shadow-none border-0 bg-transparent'>
                        <img src='~/assets/img/op.png' class='img-botbar'>
                        <br>
                        <small v-bind:class="[aktif == '/op' ? 'text-white' : '']">OP</small>
                    </button>
                </li>
                <li class="nav-item">
                    <button @click='redirect("/ed")' v-bind:class="[aktif == '/ed' ? '' : 'botbar']" class='text-secondary shadow-none border-0 bg-transparent'>
                        <img src='~/assets/img/ed.png' class='img-botbar'>
                        <br>
                        <small v-bind:class="[aktif == '/ed' ? 'text-white' : '']">ED</small>
                    </button>
                </li>
            </ul>
        </div>
        <div class='col-sm-12 col-md-3 col-lg-3'></div>
    </div>
</div>
</template>

<style>
.img-botbar {
    width: 2rem;
    height: 2rem;
}
</style>
<script>
export default {
    data() {
        return {
            aktif: this.$route.path
        }
    },

    methods: {
        redirect(q) {
            this.$router.push({
                path: q
            })
        }
    }
}
</script>