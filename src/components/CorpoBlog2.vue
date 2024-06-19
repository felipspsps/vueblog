<script>
    export default{
        props:({
            titulo: {
                type: String,
                required: true
            },
            txt: {
                type: String,
                required: true
            },
            post: {
                type: String,
                required: true
            },
        }),
        methods:({
            truncate(value, length){
                if (value.length > length) {
                    return value.substring(0, length) + "...";
                }
                else{
                    return value;
                }
            }
        })
    }
</script>

<template>
    <div class="largura">
        <div class="cab">
            <div id="div_logo">
                <span>
                    <img :src="post" width="100%">
                </span>
            </div>
            <div id="div_titulo">
                <span>{{ titulo }}</span>
            </div>
            <div id="div_txt">
                <span>{{ truncate(txt, 200) }}</span>
            </div>
        </div>
    </div>
</template>

<style scoped>
#div_titulo{
    color: red;
    font-family: 'Times New Roman';
}
#div_txt{
    font-family: 'Arial';
}
.cab{
    text-align: justify;
}
.largura{
    width: 85%;
    align-items: center;
    margin: auto;
}
</style>