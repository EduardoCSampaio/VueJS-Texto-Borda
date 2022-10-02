<script setup>
import { ref, computed } from 'vue'

const message = ref('Escreva aqui')
const color = ref('#333')
const size = ref(12)
const bordercolor = ref('#333')
const borderstyle = ref('Escreva o Tipo da Sua Borda')
const borderwidth = ref(5)

const h1_style = computed(() => {
  return ({
  	color: color.value,
 		fontSize: `${size.value}pt`,	
    borderWidth: `${borderwidth.value}pt`,
    borderStyle: borderstyle.value,
    borderColor: bordercolor.value
  });
})
</script>

<template>
  
  <h1>
    Tipos de Bordas
  </h1>
	<p>
    None: sem borda -
		Hidden: equivalente a none -
		Dotted: borda pontilhada -
		Dashed: borda tracejada -
		Solid: borda contínua -
		Double: borda dupla -
		Groove: borda entalhada -
		Ridge: borda em ressalto -
		Inset: borda em baixo relevo -
		Outset: borda em alto relevo.
  </p>
  
 <div>  
  <input type="color" v-model="color" /> Cor da Letra
 </div>
  <div>
   	<input type="range" v-model="size" /> Tamanho da Letra
  </div>
  <div>
  	<input v-model="message">
  </div>
  	<input type="color" v-model="bordercolor" /> Cor Da Barra
  <div>
    <input type="range" v-model="borderwidth" /> Tamanho da Barra
  </div>
  <div>
    <input type="text" v-model="borderstyle" />
  </div>
  <h3 :style=h1_style>{{ message }}</h3>
</template>
