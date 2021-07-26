<template>
    <ion-header :translucent="true">
        <div class="container">
            <ion-button router-link="/home">Home</ion-button>
            <ion-button router-link="/about">About</ion-button>
            <ion-button router-link="/events">Events</ion-button>
        </div>
    </ion-header>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
import {  IonHeader, IonButton, /*IonToolbar*/ } from '@ionic/vue';


export default defineComponent({
    name: 'Header',
    components: {
        IonHeader,
        // IonToolbar,
        IonButton
    }
})
</script>

<style scoped>
    ion-header {
        display: flex;
        justify-content: space-around;
        align-items: center;
        /* padding: 0 5em; */
        /* --background: rgba(0, 0, 0, 0.9); */
    }

    .container {
        padding: .5% 0;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10%;
        background: rgba(0, 0, 0, 0.95);
    }

    ion-toolbar {
        display: block;
        /* padding: 0 12%; */
        box-sizing: border-box;
    }

    .container ion-button {
        --background: rgba(169,3,41,1);
        --background: -moz-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: -webkit-gradient(left top, right top, color-stop(0%, rgba(169,3,41,1)), color-stop(44%, rgba(143,2,34,1)), color-stop(100%, rgba(109,0,25,1)));
        --background: -webkit-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: -o-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: -ms-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: linear-gradient(to right, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#a90329', endColorstr='#6d0019', GradientType=1 );
        --color:#ffffff;
    }
</style>