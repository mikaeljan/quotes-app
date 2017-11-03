<template>
    <div class="quotes">
        <!--@click.native=''-->
        <quote-comp
                @click.native='removeQuote(index)'
                v-for="(quote, index) in quotes"
                :quote='quote'
                :key='index'>{{quote.message}}

        </quote-comp>
    </div>
</template>

<script>
    import Quote from './Quote.vue'

    export default {
        props: ['quotes'],
        components: {
            'quote-comp': Quote
        },
        methods:{
            removeQuote(index){
                this.quotes.splice(index,1);
            }
        }
    }
</script>

<style scoped>
    button {
        display: block;
        margin: auto;
    }
</style>