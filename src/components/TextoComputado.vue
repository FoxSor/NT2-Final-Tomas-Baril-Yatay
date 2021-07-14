<template>
    <div>
    <input 
        type="text"
        v-model="text" 
    >
    <p>cantidad: {{text.length}}</p>
    <p>{{ text | codificar }} (codificado)</p>
    <p>{{ text.toUpperCase() }} (Mayúscula)</p>
    <p>{{ text.toLowerCase() }} (Minúscula)</p>
    <p>{{ text | mayusculaMinuscula }} (Mayúscula/Minúscula)</p>
    <p>{{ text | minusculaMayuscula }} (Minúscula/Mayúscula)</p>

    <h1>respuestas: 1=b, 2=b, 3=c, 4=b, 5=b</h1>
    
  </div>
</template>


<script>
    export default{
        data() {
            return{
                text: ''
            }
        }, 
        filters: {
            codificar (texto) {
                let nuevoTexto = texto.toLowerCase()
                nuevoTexto = nuevoTexto.replace(/a|e|o|u/gi, function (x) {
                switch(x){
                    case "a":
                        return "u"
                    case "e":
                        return "o"
                    case "o":
                        return "e"
                    case "u":
                        return "a"
                }
                 });
                return nuevoTexto
            },
            mayusculaMinuscula (texto) {
                let letras = texto.toLowerCase().split("");
                for (let i = 0; i < letras.length; i++) {
                    if(i % 2 === 0){
                        letras[i] = letras[i].toUpperCase();
                    }
                }
                return letras.join("");
            },
            minusculaMayuscula (texto) {
                let letras = texto.toUpperCase().split("");
                for (let i = 0; i < letras.length; i++) {
                    if(i % 2 === 0){
                        letras[i] = letras[i].toLowerCase();
                    }
                }
                return letras.join("");
            }
        }   
    }   
</script>