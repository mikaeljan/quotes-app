<template>
    <div class="progress">
        <div :style='barStyle' class="progress-bar" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
            {{counter}} / {{quoteLimit}}
        </div>
    </div>
</template>

<script>
export default {
    props: ["counter",'quoteLimit'],
    computed: {
        barStyle() {
            if (this.counter >= this.quoteLimit) {
                return {
                    "width": 100 + '%'
                }
            } else {
                return {
                    "width": (this.counter * 10) + '%'
                }
            }
        }

    }
}
</script>

<style scoped>
    .progress-bar{
        transition: width 800ms;
    }
</style>