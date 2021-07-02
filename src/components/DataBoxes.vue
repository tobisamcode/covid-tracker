<template>
    <div class="grid gap-4 md:grid-cols-2">
    <!-- BOX 1 -->
        <div class="p-10 text-center bg-pink-100 shadow-md">
            <h3 class="mb-4 text-3xl font-bold text-pink-900">Cases</h3>

            <div class="mb-4 text-2xl">
                <span class="font-bold">New:</span> {{numberWithCommas(stats.NewConfirmed)}}
            </div>
            <div class="mb-4 text-2xl">
                <span class="font-bold">Total:</span> {{numberWithCommas(stats.TotalConfirmed)}}
            </div>
        </div>

        <!-- BOX 2 -->
        <div class="p-10 text-center bg-pink-200 shadow-md">
            <h3 class="mb-4 text-3xl font-bold text-pink-900">Deaths</h3>

            <div class="mb-4 text-2xl">
                <span class="font-bold">New:</span> {{numberWithCommas(stats.NewDeaths)}}
            </div>
            <div class="mb-4 text-2xl">
                <span class="font-bold">Total:</span> {{numberWithCommas(stats.TotalDeaths)}}
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: 'DataBoxes',
    props: ['stats'],
    methods: {
        numberWithCommas(x){
            return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
        }    
    }
}
</script>