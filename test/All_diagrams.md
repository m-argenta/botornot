# Diagramas: Bot or Not

### Interacción

```markdown
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
```

### Contexto

```markdown
<pre class="mermaid">
flowchart LR
B((Start)) --> 		B1(Situación 1: se presenta una imagen descriptiva de un escenario común, y tres imágenes como opciones de respuesta, habiendo una que encaja mejor con el escenario planteado.)
    				B1 --> 		B1h([Escoge la imagen correcta.]) 
								B1h --> B2(Situación 2: se presenta una imagen descriptiva de un problema común, y tres imágenes como opciones de respuesta, habiendo una que podría usarse como herramienta no-convencional para solucionar el problema planteado.)
    				B1 --> 		B1i([Escoge una imagen incorrecta.]) 
								B1i -->|Robot +1| B2
								
					B2 --> 		B2h([Escoge la imagen correcta.]) 
								B2h --> B3(Situación 3: se presenta una imagen descriptiva de un conjunto de objetos contenidos en un sistema de almacenamiento común, y tres imágenes como opciones de respuesta, habiendo una que encaja mejor que las demás en el contexto planteado.)
					B2 --> 		B2i([Escoge una imagen incorrecta.]) 
								B2i -->|Robot +1| B3
								
            		B3 --> 		B3h([Escoge la imagen correcta.]) 
								B3h --> End2((Fin))
            		B3 --> 		B3i([Escoge una imagen incorrecta.]) 
								B3i-->|Robot +1| End2
</pre>
```

### Narrativa

```markdown
<pre class="mermaid">
flowchart LR
C((Start)) --> 		C1(Secuencia de tres: se presentan ocho cartas con diferentes iconos. En ellas hay unos cubiertos, un zapato, un grifo, unas tijeras, unos cordones, un mando de televisión, una lámpara y unos calcetines.)
					C1 --> 		C1s1{¿Primera carta escogida?}
								C1s1 --> 	C1h1([Escoge en primer lugar los calcetines.])
											C1h1 --> C1s2{¿Segunda carta escogida?}
								C1s1 --> 	C1i1([No escoge en primer lugar los calcetines.])
											C1i1 -->|Robot +1| C1r1((Reiniciar la secuencia))
											
								C1s2 -->	C1h2([Escoge en segundo lugar los zapatos.])
											C1h2 --> C1s3{¿Tercera carta escogida?}
								C1s2 --> 	C1i2([No escoge en segundo lugar los zapatos.])
											C1i2 -->|Robot +1| C1r2((Reiniciar la secuencia))
											
								C1s3 -->	C1h3([Escoge en tercer lugar los cordones.])
											C1h3 --> End3((Fin))
								C1s3 --> 	C1i3([No escoge en tercer lugar los cordones.])
											C1i3 -->|Robot +1| C1r3((Reiniciar la secuencia))
</pre>
```

### Significado

```markdown
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
```

### Desobediencia

```markdown
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
```

<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({
		startOnLoad: true,
		theme: 'dark'
	});
</script>
