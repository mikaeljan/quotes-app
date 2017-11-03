<template>
    <div class="">
        <div class="container">
            <header-comp>
                <h2 slot='title'>Quotes Added</h2>
            </header-comp>
            <hr>

            <progress-bar-comp
                    :quoteLimit='quoteLimit'
                    :counter='numberOfQuotes'
            >
            </progress-bar-comp>
            <hr>

            <add-quote-comp
                    :quotes='quotes'
                    :quoteLimit='quoteLimit'
                    @addQuote='quotes = $event'
                    @removeQuote='quotes = $event'
            >

            </add-quote-comp>
            <hr>
            <quotes-comp :quotes='quotes'>

            </quotes-comp>



        </div>
        <div class="container">
            <footer-comp></footer-comp>
        </div>

    </div>

</template>

<script>
    import Header from './components/Shared/Header.vue'
    import Footer from './components/Shared/Footer.vue'
    import AddQuote from './components/Quotes/AddQuote.vue'
    import Quotes from './components/Quotes/Quotes.vue'
    import ProgressBar from './components/Shared/ProgressBar.vue'

    export default {
        components: {
            'header-comp': Header,
            'footer-comp': Footer,
            'progress-bar-comp': ProgressBar,
            'add-quote-comp': AddQuote,
            'quotes-comp': Quotes
        },
        data(){
            return {
                quoteLimit:10,
                quotes: [
                    {
                        message: 'A lovely quote!'
                    },
                    {
                        message: 'Oh Look! Another!'
                    }
                ]
            }
        },
        computed: {
            numberOfQuotes(){
                return (this.quotes.length);
            }
        },

    }
</script>

<style scoped>
    .alert {
        text-align: center;
        margin: 20px 0;
    }
</style>
