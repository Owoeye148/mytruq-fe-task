<template>
    <ion-page>
        <Header />
        <ion-content>
            <div class="container">
                <h1>About</h1>
                <h2>Version 1.0.0</h2>
                <p>
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempore ratione nostrum aspernatur. 
                    Tempore a deserunt veritatis, officia mollitia laboriosam vero
                    nihil beatae soluta ullam magni reprehenderit non ex libero architecto!

                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempore ratione nostrum aspernatur. 
                    Tempore a deserunt veritatis, officia mollitia laboriosam vero
                    nihil beatae soluta ullam magni reprehenderit non ex libero architecto!
                </p>
                <p>
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempore ratione nostrum aspernatur. 
                    Tempore a deserunt veritatis, officia mollitia laboriosam vero
                    nihil beatae soluta ullam magni reprehenderit non ex libero architecto!

                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempore ratione nostrum aspernatur. 
                    Tempore a deserunt veritatis, officia mollitia laboriosam vero
                    nihil beatae soluta ullam magni reprehenderit non ex libero architecto!
                </p>
            </div>     
        </ion-content>
    </ion-page>
</template>

<script>
import { IonContent, IonPage } from '@ionic/vue';
import Header from '../Components/Header.vue';

export default {

    components: {
        IonContent,
        IonPage,
        Header
    },
    setup () {
        

        return {}
    }
}
</script>

<style scoped>
    ion-content {
        --background: rgb(30, 27, 27);
    }

    .container {
        width: 70%;
        margin-left: 10%;
        margin-top: 5%;
        color: white;
    }


</style>