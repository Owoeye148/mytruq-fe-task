<template>
    <ion-page>
        <Header />
        <ion-content>
            <div class="searchbar">
                <h2>SEARCH FOR UPCOMING EVENTS BY ARTISTS</h2>
                <input type="text" v-model="search" placeholder="enter artist name">
                <ion-button @click="fetchText()" class="jolly-btn">SEARCH</ion-button>
            </div>
            <div class="dta-container">
                <div class="dta" v-if="loaded">
                    <div class="artist-img-text"> 
                        <img class="artist-image" :src='details[0].artist.image_url' :alt="details[0].artist.name">
                        <p>{{ search }}</p>
                    </div>
                    <div class="upcoming">Upcoming Events</div>
                    <div class="upcoming-events" v-for="detail in details" :key="detail.id">
                        <div class="date-location">
                            {{ detail.datetime.substring(0, 10) }}
                            <div>
                                {{ detail.venue.name }}
                                <div class="city-region">
                                    {{ detail.venue.city }}
                                    {{ detail.venue.region }}
                                </div>
                                <!-- {{ detail.venue.country }} -->
                            </div>
                        </div>
                        <div class="tickets">
                            <a :href="detail.offers[0].url">Tickets &amp; More</a>
                        </div>
                    </div>
                </div>
            </div>
        </ion-content>
    </ion-page>
</template>

<script lang="ts">
import { IonContent, /*IonHeader,*/ IonPage, IonButton, /*IonToolbar, IonSearchbar*/ } from '@ionic/vue';
import { defineComponent } from 'vue'
import axios from 'axios';
import Header from '../Components/Header.vue';

export default defineComponent({
    name: 'Home',
    data() {
        return {
            stop: false,
            search: '',
            details: [],
            loaded: false,
            artistName: '',
            picture: '',
            location: '',
            eventTitle: ''
        }
    },
    components: {
        IonContent,
        // IonHeader,
        IonPage,
        IonButton,
        Header
        // IonToolbar,
        // IonSearchbar
    },

    methods: {
        
        async fetchText() {
            await axios.get(`https://rest.bandsintown.com/artists/${this.search}/events?app_id=1&date=upcoming`)
                .then(response => this.details = response.data)
                this.loaded = true
                console.log(this.details)
        }
    }
})
</script>

<style scoped>
    ion-content {
        --background: rgb(30, 27, 27);
    }

    .searchbar {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
        margin-top: 5%;
        margin-bottom: 2%;
    }

    .searchbar h2 {
        color: #fff;
        text-align: center;
        font-size: 100%;
    }

    .searchbar input {
        width: 40%;
        height: 2.5em;
        border-radius: 50px;
        border: none;
        text-align: center;
    }

    .jolly-btn{
        --background: rgba(169,3,41,1);
        --background: -moz-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: -webkit-gradient(left top, right top, color-stop(0%, rgba(169,3,41,1)), color-stop(44%, rgba(143,2,34,1)), color-stop(100%, rgba(109,0,25,1)));
        --background: -webkit-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: -o-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: -ms-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        --background: linear-gradient(to right, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#a90329', endColorstr='#6d0019', GradientType=1 );
    
    
        --color:#ffffff;
        margin-top: 1%;

    }

    .dta-container {
        display: flex;
        align-items: center;
        justify-content: center;
        margin-left: 5%;
        margin-right: 5%;
    }

    .dta {
        color: white;
    }

    .artist-img-text {
        display: flex;
        align-items: center;
        gap: 0;
        background-color: rgba(0, 0, 0, 0.4);
        /* margin: 1em; */
        border-radius: 10px;
        width: 100%;
    }

    .artist-image {
        width: 15%;
        margin: 1em;
        border-radius: 100px;
    }
    .dta-text {
        color: white;
    }

    .upcoming {
        margin: 1em 0;
        font-weight: bold;
        font-size: 2em;
    }

    .upcoming-events {
        display: flex;
        justify-content: space-between;
        width: 100%;
        /* margin: 1em; */
        border: 1px solid rgba(169,3,41,1);
        border-radius: 5px;
        padding: 1em;
        margin-bottom: .8em;
    }

    .date-location {
        display: flex;
        gap: 2em;
    }

    .upcoming-events .tickets {
        display: flex;
        align-items: center;
        background: rgba(169,3,41,1);
        background: -moz-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        background: -webkit-gradient(left top, right top, color-stop(0%, rgba(169,3,41,1)), color-stop(44%, rgba(143,2,34,1)), color-stop(100%, rgba(109,0,25,1)));
        background: -webkit-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        background: -o-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        background: -ms-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        background: linear-gradient(to right, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#a90329', endColorstr='#6d0019', GradientType=1 );
        padding: 0.7em 1em;
        color:#ffffff;
        border-radius: 5px;
    }

    .upcoming-events a {
        text-decoration: none;
        color: #fff;
    }
</style>