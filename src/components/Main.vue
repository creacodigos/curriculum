<template>
  <main class="wrapper">
    <cr-columna-1></cr-columna-1>
    <cr-columna-2></cr-columna-2>
    <cr-columna-3></cr-columna-3>
  </main>
</template>

<script>
import Columna1 from './Columna1';
import Columna2 from './Columna2';
import Columna3 from './Columna3';
import data from "../assets/data/data.json";

export default {
	name: 'CrMain',
	components: {
		'cr-columna-1': Columna1,
		'cr-columna-2': Columna2,
		'cr-columna-3': Columna3
	},
    data() {
        return {
            elements: data
        };
    }
}
</script>