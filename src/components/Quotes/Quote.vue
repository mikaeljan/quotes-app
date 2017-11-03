<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div
                    class="panel-body quote">
                <slot></slot>
            </div>
        </div>

    </div>
</template>

<script>
    import {vm} from '../../main.js'
export default {
    props:['quote'],
}
</script>

<style>
    .panel-body{
        font-size:24px;
        color:#6e6e6e;
        font-family:'Arizonia', cursive;
    }
    .panel:hover {
        background-color: lightsalmon;
    }
    .quote {
        cursor: pointer;
    }
</style>