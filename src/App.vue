<template>
    <div id="app">
        <BarChart id="c1" v-bind:option="chartData"></BarChart>
    </div>
</template>

<script>
    import BarChart from "~/components/BarChart";

    export default {
        components: {
            BarChart
        },
        data() {
            return {
                chartData: {
                    title: {
                        text: 'ECharts组件化开发'
                    },
                    tooltip: {},
                    legend: {
                        data: ['销量']
                    },
                    xAxis: {
                        data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
                    },
                    yAxis: {},
                    series: [{
                        name: '销量',
                        type: 'bar',
                        data: [5, 20, 36, 10, 10, 20]
                    }]
                }
            }
        },
        created() {
        },
        methods: {}
    }
</script>
<style>
</style>
