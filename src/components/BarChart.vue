<template>
    <section>
        <!--注意id动态绑定，并设置宽高-->
        <div :id="id" style="width:800px; height:500px"></div>
    </section>
</template>
<script>
    import echarts from 'echarts'

    export default {
        name: "BarChart",
        // option 支持动态赋予数据
        props: ['id', 'option'],
        data() {
            return {
                // 目标 chart，以便后续进行操作
                chart: null
            }
        },
        created() {
        },
        mounted() {
            // 注意等 echarts的图形容器生成，再对其进行初始化
            this.initChart();
        },
        methods: {
            initChart() {
                // 基于准备好的dom，初始化echarts实例，为了通用复用，id必须动态绑定
                this.chart = echarts.init(document.getElementById(this.id));
                // 初始化数据
                this.chart.setOption(this.option)
            }
        }
    }
</script>