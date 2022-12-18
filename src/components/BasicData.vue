<template>
    <div v-if="dailyData" class="w-100 p-3 text-light">
        <h1 class="display-3 mb-0">{{ currentTemperature }}°C</h1>
        <span class="text-light opacity-75">{{ currentData.weather[0].description }}</span>

    </div>


    <!-- <h6 class="display-7 m-3">{{ getDate(currentData.dt) }}</h6> -->
    <div class="h-100 w-100 p-3 d-flex flex-row" v-if="dailyData">
        <div class="card bg-dark m-2" style="text-align: center;">
            <div class="card-body">
                <span class="text-white-50">{{dailyData.list[0].dt_txt.slice(0,10)}}</span>
                <p>{{dailyData.list[0].dt_txt.slice(11,16)}}</p>
                <p>{{ Math.round(dailyData.list[0].main.temp)}}°C</p>
            </div>
            <img src="@/assets/sun.png" alt="sun" class="mx-auto" style="height: 75px;">
        </div>
        <div class="card bg-dark m-2" style="text-align: center;">
            <div class="card-body">
                <span class="text-white-50">{{dailyData.list[1].dt_txt.slice(0,10)}}</span>
                <p>{{dailyData.list[1].dt_txt.slice(11,16)}}</p>
                <p>{{ Math.round(dailyData.list[1].main.temp)}}°C</p>
            </div>
            <img src="@/assets/sun.png" alt="sun" class="mx-auto" style="height: 75px;">
        </div>
        <div class="card bg-dark m-2" style="text-align: center;">
            <div class="card-body">
                <span class="text-white-50">{{dailyData.list[2].dt_txt.slice(0,10)}}</span>
                <p>{{dailyData.list[2].dt_txt.slice(11,16)}}</p>
                <p>{{ Math.round(dailyData.list[2].main.temp)}}°C</p>
            </div>
            <img src="@/assets/sun.png" alt="sun" class="mx-auto" style="height: 75px;">
        </div>
        <div class="card bg-dark m-2" style="text-align: center;">
            <div class="card-body">
                <span class="text-white-50">{{dailyData.list[3].dt_txt.slice(0,10)}}</span>
                <p>{{dailyData.list[3].dt_txt.slice(11,16)}}</p>
                <p>{{ Math.round(dailyData.list[3].main.temp)}}°C</p>
            </div>
            <img src="@/assets/sun.png" alt="sun" class="mx-auto" style="height: 75px;">
        </div>
        <div class="card bg-dark m-2" style="text-align: center;">
            <div class="card-body">
                <span class="text-white-50">{{dailyData.list[4].dt_txt.slice(0,10)}}</span>
                <p>{{dailyData.list[4].dt_txt.slice(11,16)}}</p>
                <p>{{ Math.round(dailyData.list[4].main.temp)}}°C</p>
            </div>
            <img src="@/assets/sun.png" alt="sun" class="mx-auto" style="height: 75px;">
        </div>

       
    </div>
</template>

<script>

export default {

    props: {
        currentData: Object,
        dailyData: Object,

    },
    computed: {
        currentTemperature() {
            console.log(this.dailyData.list);
            console.log(this.currentData.main.temp)
            return Math.round(this.currentData.main.temp)
        },
        getDate(unix) {
            let data = new Date(unix * 1000);
            return data.toLocaleString();
        }
    }
}
</script>

<style scoped>

</style>