# Actividades de Búsqueda de Similitud Secuencial

### PARA PENSAR 🤔: Ingresá al servidor del NCBI y mirá los distintos programas derivados del BLAST que se ofrecen ¿Para qué sirve cada uno? ¿En qué casos usarías cada uno?

- **blastp (protein-protein BLAST):** Compara una secuencia de aminoácidos contra una base de datos de proteínas.
  - **Caso de uso:** Encontrar homólogos de una proteína, predecir su función o buscar miembros de una familia de proteínas.

- **blastn (nucleotide-nucleotide BLAST):** Compara una secuencia de ADN/ARN contra una base de datos de nucleótidos.
  - **Caso de uso:** Encontrar dónde se localiza un gen en un genoma, buscar secuencias de ARN ribosómico para identificación taxonómica o encontrar genes similares en otras especies.

- **blastx (translated nucleotide-protein BLAST):** Toma una secuencia de nucleótidos, la traduce en los 6 marcos de lectura posibles y compara esas traducciones contra una base de datos de proteínas.
  - **Caso de uso:** Evaluar fragmentos de ADN de carácter codificante desconocido para determinar similitudes con proteínas e identificar nuevos genes.

- **tblastn (protein-translated nucleotide BLAST):** Toma una secuencia de proteína y la compara contra una base de datos de nucleótidos que ha sido traducida dinámicamente en los 6 marcos de lectura.
  - **Caso de uso:** Localizar el gen específico que codifica una proteína determinada dentro de un genoma que carece de anotación previa.

- **tblastx (translated nucleotide-translated nucleotide BLAST):** Compara las 6 traducciones de una secuencia de nucleótidos contra las 6 traducciones de una base de datos de nucleótidos.
  - **Caso de uso:** Encontrar relaciones muy distantes entre secuencias de nucleótidos que no se pueden detectar de otra manera.

---

## 🧗🏻‍♀️ Desafío 7

*Nota: la herramienta me permite fijar un máximo de 5000 "max target sequences".*

### E-value vs. % Identidad
El **E-value** es la probabilidad de que el parecido de las secuencias sea pura coincidencia o un error al azar, por eso buscamos que sea lo más cercano a cero posible. El **% de identidad** es qué tan parecidas son las secuencias. Si dos secuencias son muy parecidas (alto % de identidad), la probabilidad de que sea por error es casi cero (E-value bajo). A mayor parecido, menor es el E-value.

### Score vs. % Identidad
El **Score** funciona como el puntaje de un juego donde cada letra que coincide exactamente suma puntos y las que no coinciden restan. Entonces, si la secuencia encontrada tiene muchas letras iguales a la dada (alto % de identidad), el sistema le otorgará un puntaje (score) mucho más alto. Más parecido es igual a más puntos.

### Score vs. E-value
Uniendo las otras dos ideas, si un alineamiento logró acumular muchos puntos (Score alto) porque las secuencias coinciden muy bien, la probabilidad de que ese resultado sea una simple coincidencia al azar es casi nula (E-value muy cercano a cero). A mayor puntaje de Score, más bajo y confiable es el E-value.


### Resultado:
Para la secuencia VVGGLGGYMLGSAMSRPIIHFGSDYEDRYYRENMHRYPNQVYYRPMDEYSNQNNFVHDCVNITIKQHTVTTTTKGENFTETDVKMMERVVEQMCITQYERESQAYYQRGSSMVLFSSPPVILLISFLIFLIVG

Por el max score es prion protein [Homo sapiens]

https://www.ncbi.nlm.nih.gov/protein/AAR21603.1?report=genbank&log$=prottop&blast_rank=2&RID=CZXVWNS7014

---

## 🧗🏻‍♀️ Desafío 8

La longitud de la secuencia es fundamental para el valor estadístico. A mayor longitud de la secuencia de entrada (query), más información tiene el algoritmo para distinguir entre una verdadera relación evolutiva (homología) y una coincidencia al azar.

Las secuencias cortas tienen menor poder discriminatorio. Cuando una secuencia es muy pequeña, es difícil acumular suficiente puntaje (score), lo que hace que los E-values sean altos y no se pueda asegurar si los resultados encontrados son realmente parientes evolutivos o simple ruido estadístico.

---

## 🧗🏻‍♀️ Desafío 9

### Utilizando BLAST utilice búsquedas de similitud secuencial para identificar a la siguiente proteína:
MIDKSAFVHPTAIVEEGASIGANAHIGPFCIVGPHVEIGEGTVLKSHVVVNGHTKIGRDNEIYQFASIGEVNQDLKYAGEPTRVEIGDRNRIRESVTIHRGTVQGGGLTKVGSDNLLMINAHIAHDCTVGNRCILANNATLAGHVSVDDFAIIGGMTAVHQFCIIGAHVMVGGCSGVAQDVPPYVIAQGNHATPFGVNIEGLKRRGFSREAITAIRNAYKLIYRSGKTLDEVKPEIAELAETYPEVKAFTDFFARSTRGLIR

Proteína:
MULTISPECIES: acyl-ACP--UDP-N-acetylglucosamine O-acyltransferase [Pseudomonadati]

### ¿Cuál es la función de la proteína?
La proteína acil-ACP--UDP-N-acetilglucosamina O-aciltransferasa (conocida como LpxA) cumple una función vital en el metabolismo bacteriano:
- Biosíntesis del lípido A: Cataliza la primera etapa de la biosíntesis del lípido A, el cual es el componente anclaje de los lipopolisacáridos (LPS) ubicados en la membrana externa de las bacterias gramnegativas.
- Transferencia de acilo: Se encarga de transferir una cadena de acilo (desde la proteína transportadora de acilo o ACP) al grupo hidroxilo del UDP-N-acetilglucosamina.

### ¿A qué grupo taxonómico pertenece?
Pseudomonadati es un reino o superclado procariota que comprende principalmente a las bacterias didérmicas o gramnegativas y sus grupos emparentados.

### A un nivel de significancia estadística adecuado ¿cuántas secuencias similares se encuentran?
100
https://blast.ncbi.nlm.nih.gov/Blast.cgi#alnHdr_WP_000565966

---

## 🧗🏻‍♀️ Desafío 10

### ¿Se obtienen los mismos resultados?
No, ahora el primer resultado es: UDP N-ACETYLGLUCOSAMINE O-ACYLTRANSFERASE [Escherichia coli K-12]

Al ingresar la secuencia en BLASTp contra la base de datos general los primeros hits arrojan la descripción exacta de la proteína junto con el organismo de origen, permitiendo definir su rol biológico y su especie taxonómica.
Contra la base de datos PDB no se obtienen los mismo resultados porque la base de datos PDB contiene exclusivamente proteínas cuyas estructuras tridimensionales fueron resueltas experimentalmente, por lo que es más pequeña que la base de datos general nr.

### ¿Qué tipo de resultados (hits) se recuperan?
Se recuperan registros estructurales tridimensionales validados identificados con códigos de 4 caracteres de la PDB. Mostrando alineamientos con aquellas proteínas homólogas de las que se conoce su estructura atómica.

### ¿Cuándo nos podría ser útil este modo de corrida?
Puede ser útil para realizsr modelado por homología o analizar la conformación espacial y estabilidad de una proteína basándose en datos reales.

