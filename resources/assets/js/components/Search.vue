<template>
    <div>
        <div class="w3-row w3-padding-8 w3-theme-d2 w3-xlarge">
            <div class="w3-quarter">
                <div class="w3-bar">
                    <a @click="w3_open" class="w3-bar-item w3-button"><i class="fa fa-bars"></i></a>
                </div>
            </div>
            <div class="w3-half">
                <slot></slot>
            </div>
            <div class="w3-quarter">
                <div class="w3-bar w3-xlarge">
                    <a href="#" class="w3-bar-item w3-button w3-left"><i class="fa fa-search"></i></a>
                    <router-link :to="{ name: 'checkout' }" class="w3-bar-item w3-button w3-right"><i
                            class="fa fa-shopping-cart"></i></router-link>
                </div>
            </div>
        </div>
    </div>

</template>
<script>
    import {eventBus} from './../app'
    export default{
            data(){
                return{
                    sideBar: false
                }
            },
            methods:{
                w3_open(){
                    this.sideBar = !this.sideBar
                    eventBus.toggleState(this.sideBar)
                }
            }
        }


</script>