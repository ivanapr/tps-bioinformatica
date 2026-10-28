## 🧗🏻‍♀️DESAFÍO I: Detalla las tácticas y/o metodologías que deberían utilizarse para darles una respuesta a los padres del niño. Dadas las secuencias de Mosca, humano y Moscahumano ¿Qué criterios se les ocurren para comparar las secuencias? ¿Qué resultados obtienen del análisis anterior? ¿Qué resultado esperaría obtener si utilizara el resto de las secuencias en el análisis? ¿Por qué?

### Tácticas y metodologías para los padres:
Para dar una respuesta científica y basada en datos tendríamos que recurrir a la inferencia evolutiva y a la filogenética molecular, secuenciar el gen Cyt P450 del niño-mosca y analizar las relaciones de homología con las demás especies.

### Criterios para comparar las secuencias:
Hacer un buen alineamiento de secuencias para establecer las correspondencias posicionales correctas en la evolución. Luego comparar las secuencias midiendo el porcentaje de identidad, las diferencias acumuladas y estimando las distancias evolutivas entre ellas.

### Resultados del análisis anterior:
Al comparar al bartmosca con el humano y la mosca supongo que obtendríamos valores de distancia que nos dirían numéricamente qué tan emparentada está esta secuencia con cada uno de esos dos organismos.

### Resultado con el resto de las secuencias y por qué:
Si sumamos el resto de las secuencias del archivo al análisis esperaría ver un árbol filogenético donde las especies se agrupen en clados claros (separando por ejemplo a los insectos de los vertebrados). Porque las secuencias elegidas tienen que ser informativas y reflejar la historia de ascendencia común, lo que nos permitiría ver con claridad si el caso del niño-mosca tiene algún sentido evolutivo o si se trata de una anomalía o contaminación en los datos.



## 🧗🏻‍♀️DESAFÍO II: Como vimos anteriormente existen algunos softwares optimizados para confeccionar alineamientos de secuencias. En particular hemos trabajado con Clustal (Larkin et al. 2007). Confecciona el alineamiento para el punto I.
Se adjunta el archivo clustalo-bartmosca.aln-clustal_num


## 🧗🏻‍♀️DESAFÍO III: Mediante el uso del servidor de IQtree (Trifinopoulos et al. 2016), confecciona los árboles filogenéticos para los alineamientos obtenidos en el punto II. Como vemos, el servidor nos permite elegir el modelo de sustitución ¿A qué se refiere? ¿Qué es el Bootstrap? ¿De qué manera nos habla de la calidad de nuestro árbol? ¿Cómo influye el número de Bootstraps en el resultado? Interpreten los resultados obtenidos, mediante la visualización de los árboles con la herramienta FigTree. ¿Es necesario realizar algún paso extra, previo a la interpretación del árbol? ¿Por qué?

Usé NGPhylogeny.fr porque IQTree está caído.
### Resultado: https://ngphylogeny.fr/workspace/history/24cd050937759db6

### ¿A qué se refiere el modelo de sustitución?
Es el modelo matemático que le indica al software cómo estimamos que cambian los aminoácidos o nucleótidos a lo largo del tiempo. Como algunas sustituciones ocurren más seguido que otras por cuestiones químicas, los modelos ajustan esas probabilidades para que el cálculo de la distancia sea lo más real posible.

### ¿Qué es el Bootstrap, cómo habla de la calidad y cómo influye su número?

El Bootstrap es un método estadístico que hace miles de "pseudoréplicas" de nuestros datos para ver si las agrupaciones (ramas) de nuestro árbol se sostienen o cambian.
Nos habla de la confianza o soporte de cada nodo. Si una rama tiene un valor alto de Bootstrap (por ejemplo cerca al 100% o 1) significa que ese agrupamiento es muy robusto y confiable.
Si usamos un número muy bajo de réplicas (como 10), el resultado es muy inestable; por eso se suelen usar al menos 1000 Bootstraps para tener una estimación estadística sólida y confiable.

### ¿Es necesario realizar algún paso extra, previo a la interpretación del árbol? ¿Por qué?
Si. Es fundamental enraizar el árbol (rooting). Los algoritmos de reconstrucción suelen generar árboles no enraizados (que muestran relaciones pero no el sentido del tiempo). Para poder interpretarlo bien para saber qué va del ancestro común hacia los descendientes actuales necesitamos definir un grupo externo (outgroup) que nos permita establecer la raíz.