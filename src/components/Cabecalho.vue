<script>
import { onMounted, onUpdated } from 'vue';

    export default {
        data() {
            return {
                botaoAtivado : true,
            };
        },
        props: {
            titulo: {
                type: String,
                required: false
            },
            logo: {
                type: String,
                required: true
            },
        },
        methods: {
            irParaLogin() {
                this.botaoAtivado = false;
                this.$router.push('/login')
            },
            getCurrentpath(){
                console.log(this.$route.path);
                return this.$route.path;
            }
        },
    }
</script>

<template>
    <nav>
        <div id="cab">
            <div id="div_logo">
                <span>
                    <img :src="logo" >
                </span>
            </div>
            <div id="login">
                <button id="b" class="btn btn-primary" @click="irParaLogin" v-if="getCurrentPath!='/login'">
                    Sair
                </button>
            </div>
            <div id="div_titulo">
                <span>{{ titulo }}</span>
            </div>
        </div>
    </nav>
</template>

<style scoped>
    nav {
        background-color: white;
        color: white;
        padding: 20px;
        right: 0px;
        width: 100%;
        position: absolute;
        top: 0px;
    }
    #cab{
        display: flex;
        justify-content: space-between;
    }
    #div_logo{
        display: flex;
        align-items: center;
        margin: auto;
    }
    #div_titulo{
        color:black;
    }
    #login{
        text-align: right;
        width: 100%;
    }
    #b{
        width: 75px
    }
</style>