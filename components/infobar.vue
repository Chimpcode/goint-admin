<style>

@font-face {
    font-family: NexaBold;
    src: url('~/static/NexaBold.otf');
}

@font-face {
    font-family: NexaLight;
    src: url('~/static/NexaLight.otf');
}

.infobar {
    position: absolute;
    height: 100%;
    width: 230px;
    right: 0;
    align-items: center;
    background-image: linear-gradient(-180deg, #833838 0%, #FF464F 100%);
    font-family: NexaBold;
}
.photo{
    margin-top: 60px;
    margin-bottom: 20px;
    width: 90px;
    height: 90px;
    border-radius: 100%;
    margin-left: 32%;
    background-color: white;

}

.tag {
    background-color: #00000087;
    font-size: 12px;
    border-radius: 10px;
}

</style>

<template>
    <div class="infobar">
        <v-layout row wrap text-xs-center>
            <div class="photo">

            </div>

        </v-layout>
        <v-layout col wrap text-xs-center style="color: white">
            <v-flex xs12>
                <h6>{{name}}</h6>
            </v-flex>
            <v-flex xs12 class="mb-3">
                <v-layout row wrap class="ml-4">
                    <v-flex xs2>
                        <img src="~/assets/invoice.png" style="width:auto; height:40px;">
                    </v-flex>
                    <v-flex xs10>
                        Plan contratado
                        <br>
                        {{literalPlan}}
                    </v-flex>
                </v-layout>
            </v-flex>
            <v-flex xs12 class="my-3">
                Rango de compañia
            </v-flex>
            <v-flex xs12 v-for="d in data" text-xs-left>
                <v-layout row wrap class="mb-3">
                    <v-flex xs4 text-xs-center>
                        <div class="tag ml-4 mr-3">
                            <div>
                                {{d.count}}
                            </div>
                        </div>
                    </v-flex>
                    <v-flex xs6 style="font-size: 11px;">
                        {{d.type}}
                    </v-flex>
                </v-layout>
            </v-flex>
        </v-layout>
    </div>



</template>

<script>
export default {
    props: ['portrait', 'name', 'plan', 'data'],
    data: () => {
        return {
            name: this.name,
            plan: this.plan,
            data: this.data
        }
    },
    computed: {
        literalPlan: function () {
            switch (this.plan) {
                case 0:
                    return '1 año, 6 meses'
                default:
                    return 'Nothing'
            }
        }

    }
}
</script>
