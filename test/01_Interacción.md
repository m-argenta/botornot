<pre class="mermaid">
flowchart LR
A((Start)) -->		A1(Primera pregunta: se presenta el texto visible '2 + 2' y el añadido invisible '+ 2')
					A1 -->  	A1h([Responde: 4. Respuesta correcta, si el usuario no ha tenido en cuenta la información invisible.]) 
            					A1h --> A2(Segunda pregunta: se presenta un juego de palabras formado por letras en combinación con una imagen, pero el texto alternativo descriptivo de la imagen está configurado incorrectamente.)
    				A1 -->  	A1b([Responde: 6. Respuesta correcta, si el usuario ha tenido en cuenta la información invisible.]) 
            					A1b -->|Robot +1| A2
    				A1 -->  	A1i([Responde: 8. Respuesta incorrecta.]) 
            					A1i -->|Random +1| A2

					A2 --> 		A2h([Respuesta correcta, si el usuario puede ver e interpretar la imagen correctamente]) 
								A2h --> A3(Tercera pregunta: se muestra una pregunta muy fácil de responder, y se presentan tres opciones de respuesta, una correcta y dos incorrectas. Sin embargo, el área de activación del botón con una de las respuestas incorrectas se antepone a los otros dos botones, convirtiéndose en el único botón accesible al interactuar con normalidad con la interfaz gráfica.)
   					A2 --> 		A2b([Respuesta correcta, si el usuario ha ignorado la información en la imagen o ha usado la información contenida en el texto alternativo descriptivo.]) 
								A2b -->|Robot +1| A3
					A2 --> 		A2i([Respuesta incorrecta, en cualquier caso.])
								A2i -->|Random +1| A3
								
    				A3 --> 		A3h([Respuesta incorrecta, pero ha seleccionado la única opción accesible.]) 
								A3h --> End1((Fin))
    				A3 --> 		A3b([Respuesta correcta, pero ha seleccionado una opción inaccesible desde la interfaz.]) 
								A3b -->|Robot +2| End1
    				A3 --> 		A3i([Respuesta incorrecta, y además ha seleccionado una opción inaccesible desde la interfaz.]) 
								A3i -->|Robot +2, Random +1| End1
</pre>

<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({
		startOnLoad: true,
		theme: 'dark'
	});
</script>
