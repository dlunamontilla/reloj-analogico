<script>
    const getDate = () => {
        const date = new Date();

        return {
            hours: date.getHours(),
            minutes: date.getMinutes(),
            seconds: date.getSeconds(),
        };
    };

    let { seconds, minutes, hours } = getDate();

    setInterval(function () {
        seconds = getDate().seconds;
        minutes = getDate().minutes;
        hours = getDate().hours;

        minutes = minutes + seconds / 60;
        hours = hours + minutes / 60;
    }, 1000);

    $: seconds = seconds;
    $: minutes = minutes;
    $: hours = hours;
</script>

<div class="reloj-container">
    <h1>Reloj analógico</h1>

    <div
        class="reloj"
        style="--seconds: {seconds * 6 + 90}deg; --minutes: {minutes * 6 +
            90}deg; --hours: {hours * 30 + 90}deg"
    >
        <div class="reloj__agujas reloj__agujas--horas" />
        <div class="reloj__agujas reloj__agujas--minutos" />
        <div class="reloj__agujas reloj__agujas--segundos" />

        <div class="reloj__hours">
            <div class="reloj__hours__9-3">
                <span>9</span>
                <span>3</span>
            </div>

            <div class="reloj__hours__12-6">
                <span>12</span>
                <span>6</span>
            </div>

            <div class="reloj__hours__indicators" />
            <div class="reloj__hours__indicators" />
            <div class="reloj__hours__indicators" />
            <div class="reloj__hours__indicators" />
        </div>
    </div>
</div>
