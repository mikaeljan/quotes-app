<template>
    <div class="row">
        <div class="col-xs-12">
            <form>
                <legend>Quote</legend>
                <div class="form-group">
                  <textarea ref='textarea' style='width: 400px; height:200px'></textarea>
                </div>
                <button
                        @click.prevent="addQuote"
                        @keydown.enter.prevent='add'
                        class="btn btn-primary">Add Quote
                </button>
            </form>
        </div>
    </div>

</template>

<script>
 export default{
     props: ['quotes','quoteLimit'],
     methods: {
         addQuote() {
             if (this.quotes.length >= this.quoteLimit) {
                 alert('Please remove some quotes before entering new ones.');
                 return;
             }
             let message = this.$refs.textarea.value;
             this.quotes.push({'message': message});
             this.$emit('quoteAdded', this.quotes);
             this.$refs.textarea.value = '';
         }
     }
 }
</script>

<style scoped>
form {
    margin: auto;
}

button,
textarea {
    display: block;
    margin: auto;
}
</style>