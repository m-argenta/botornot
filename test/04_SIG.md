<pre class="mermaid">
flowchart LR
D((Start)) --> 		D1(Pregunta de prueba: ¿Equivalente a 1 metro?) 
					D1 --> 		D1h([Respuesta correcta, marcada como preferida: 100 cm]) 
								D1h --> D2(Pregunta de prueba: ¿Equivalente a 2h 15 min?)
					D1 --> 		D1i([Respuesta incorrecta que no ha sido marcada: 1000 cm]) 
								D1i -->|Random +1| D2
					D1 --> 		D1b([Respuesta incorrecta que no ha sido marcada: 10 cm])
								D1b -->|Random +1| D2
								
					D2 --> 		D2h([Respuesta correcta, marcada como preferida: 135 min.])
								D2h --> D3(Pregunta de comprobación: ¿Cuántas pulgadas hay en 7 metros?)
					D2 --> 		D2i([Respuesta incorrecta que no ha sido marcada: 215 min.]) 
								D2i -->|Random +1| D3
					D2 --> 		D2b([Respuesta incorrecta que no ha sido marcada: 225 min.])
								D2b -->|Random +1| D3

					D3 --> 		D3h([Respuesta incorrecta, marcada como preferida: 293.18]) 
								D3h --> D4(Pregunta de comprobación: ¿Cuántos acres hay en 200 hectáreas?)
					D3 --> 		D3i([Pregunta incorrecta que no ha sido marcada: 243.66]) 
								D3i -->|Random +1| D4
					D3 --> 		D3b([Respuesta correcta que no ha sido marcada: 275.59]) 
								D3b -->|Robot +1| D4
								
					D4 --> 		D4h([Respuesta incorrecta, marcada como preferida: 374.98]) 
								D4h --> End4((Fin))
					D4 --> 		D4i([Respuesta incorrecta que no ha sido marcada: 231.73]) 
								D4i -->|Random +1| End4
					D4 --> 		D4b([Respuesta correcta que no ha sido marcada: 494.21]) 
								D4b -->|Robot +2| End4
</pre>

<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({
		startOnLoad: true,
		theme: 'default'
	});
</script>
