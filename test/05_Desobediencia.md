<pre class="mermaid">
flowchart LR
E((Start)) --> 		E1(Descifra un texto largo y responde las preguntas relacionadas)
					E1 --> 		E1h([Saltar esta pregunta]) 
								E1h --> E2(Descifra un gráfico confuso y responde las preguntas relacionadas)
					E1 --> 		E1i([Respuesta incorrecta]) 
								E1i -->|Random +1| E2
					E1 --> 		E1b([Respuesta correcta]) 
								E1b -->|Robot +1| E2
					
					E2 --> 		E2h([Saltar esta pregunta]) 
								E2h --> E3(Descifra un problema complejo de lógica y propón una solución de entre las propuestas)
					E2 --> 		E2i([Respuesta incorrecta]) 
								E2i -->|Random +1| E3
					E2 --> 		E2b([Respuesta correcta]) 
								-->|Robot +2| E3
					
					E3 --> 		E3h([Saltar esta pregunta]) 
								E3h	--> End5((Fin))
					E3 --> 		E3i([Respuesta incorrecta])
								E3i -->|Random +1| End5
					E3 --> 		E3b([Respuesta correcta]) 
								E3b -->|Robot +4| End5
</pre>

<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({
		startOnLoad: true,
		theme: 'dark'
	});
</script>
