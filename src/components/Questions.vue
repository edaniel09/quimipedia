<template>
    <div style="min-width: 100%; max-width: 100%;">
        <h2  style="color: white;">Trivia!</h2>
        <h3  style="color: white;">{{ preguntas[idxPregunta].enunciado }}</h3>
        <div v-if="estado == 'pregunta'">
            <v-btn style="margin: 10px;" small color="primary" @click="responder(true, preguntas[idxPregunta].respuesta)">Verdadero</v-btn>
            <v-btn style="margin: 10px;" small color="primary" @click="responder(false, preguntas[idxPregunta].respuesta)">Falso</v-btn>
        </div>
        <div v-else>
            <p v-if="estado == 'correcto'" style="color: green;font-size: 30px;">Contestaste bien!</p>
            <p v-else style="color: red; font-size: 30px;">Te equivocaste!</p>
            <p>{{ preguntas[idxPregunta].dato }}</p>
            <v-btn @click="escogerPregunta">Siguiente</v-btn>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            preguntas: [{
                enunciado: 'Es cierto que en Ecuador se encuentra el elemento Oro ',
                respuesta: true,
                dato: 'El Oro es uno de los metales preciosos que Ecuador tiene, así como el cobre y la plata. '
            },
            {
                enunciado: 'Minería es recolección de materia prima como minerales ',
                respuesta: true,
                dato: 'Minería es la actividad de explotar las minas, extraer minerales. '
            },
            {
                enunciado: 'Hay un total de 8 elementos químicos que se encuentran en el Ecuador  ',
                respuesta: true,
                dato: 'Son 8 elementos que encontramos en el Ecuador: Oro, plata, cobre, hierro, molibdeno, silicio, plomo y uranio.  '
            },
            {
                enunciado: 'Existe minería responsable  ',
                respuesta: true,
                dato: 'Toda empresa minera se rige por el cumplimento de normativas tanto estatales como ambientales. Al no existir un acuerdo con el estado esto es considerado, minería ilegal. '
            },
            {
                enunciado: 'La minería aporta con crecimiento nacional  ',
                respuesta: true,
                dato: 'Toda industria minera aporta con impuestos y regalías que ayudan al crecimiento nacional. Sumado al aporte que proporcionan para el desarrollo tanto de emprendimientos desde la parte agrícola hasta proyectos educativos. '
            },
            {
                enunciado: 'Muchas de las cosas que usas a diario provienen de la actividad minera  ',
                respuesta: true,
                dato: 'Desde los productos tecnológicos hasta los cimientos de las ciudades, contienen materia prima naciente de la minería. '
            },
            {
                enunciado: 'La minería en el Ecuador no aporta con empleo a los Ecuatorianos  ',
                respuesta: false,
                dato: 'Actualmente, aporta con 30000 empleos directos en diferentes proyectos. '
            },
            {
                enunciado: 'La minería aporta al PIB (Producto Interno Bruto) del Ecuador ',
                respuesta: true,
                dato: 'El PIB es importante para la desarrollo de cualquier país; en el 2020, la minería aportó con el 4% del PIB al Ecuador. '
            },
            {
                enunciado: 'El carro, el celular y la televisión contienen productos mineros  ',
                respuesta: true,
                dato: 'Un carro tiene un 82%, un celular un 45% y una TV un 78%. En donde estos varían entre elementos metálicos y no metálicos obtenida de los minerales. '
            },
            {
                enunciado: 'La mesa, la silla y los objetos plásticos contienen productos mineros ',
                respuesta: false,
                dato: 'Estos son resultados de la explotación de la madera o de actividad industrial no asociada a la minería. '
            },
            {
                enunciado: 'La Minería responsable significa destrucción al medio ambiente  ',
                respuesta: false,
                dato: 'La minería responsable implica que se realice un cuidado en el medio ambiente, tanto antes, durante y después de realizar cualquier proceso minero. '
            },
            {
                enunciado: 'Existen proyectos mineros estratégicos en desarrollo en el país ',
                respuesta: true,
                dato: 'Existen 5 proyectos estratégicos (Fruta del Norte, Rio blanco, Loma Larga, Mirador y San Carlos Panantza) ya desarrollados y otros 6 proyectos por desarrollar. '
            },
            {
                enunciado: 'La minería responsable, no sigue la ley del gobierno y solo ocasiona destrucción ambiental  ',
                respuesta: false,
                dato: 'Todo proyecto minero que se desee realizar tiene que cumplir con normativas ambientales y de seguridad establecidas en la Ley de Minería, de no hacerlo tiene que detener sus actividades. '
            }],
            idxPregunta: 0,
            estado: 'pregunta'//los posibles valores son pregunta, correcto, errado
        }
    },
    methods : {
        responder(valuein, respuestaCorrecta) {
            if (valuein == respuestaCorrecta) {
                this.estado = 'correcto'
            }
            else {
                this.estado = 'errado'
            }
        },
        escogerPregunta() {
            if(this.idxPregunta < this.preguntas.length - 1){
                this.idxPregunta = this.idxPregunta + 1
            }
            else {
                this.idxPregunta = 0
            }
            this.estado = 'pregunta'
        }
    }
}
</script>