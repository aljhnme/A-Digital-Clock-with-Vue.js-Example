<template>
    <div id="clock">
        <p class="date">{{ date }}</p>
        <p class="time">{{ time }}</p>
    </div>
</template>
<script type="text/javascript">
export default {

    name: 'IdClock',

    data() {
        return {
            date: "0000-00-00",
            time: "00:00:00",

        }
    },
    methods: {
        ShowDTnow: function() {

            const dThisNow = this;

            setInterval(function() {

                var tdATEN = new Date();
                dThisNow.date = tdATEN.getFullYear() + "-" + (tdATEN.getMonth() + 1) + "-" + tdATEN.getDate();

                dThisNow.time = tdATEN.getHours() + ":" + tdATEN.getMinutes() + ":" + tdATEN.getSeconds();

            }, 1000)
        }
    },
    mounted() {
        this.ShowDTnow();
    }
}
</script>