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
<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({
		startOnLoad: true,
		theme: 'dark'
	});
</script>
