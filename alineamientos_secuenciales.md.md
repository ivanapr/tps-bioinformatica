# Actividades de B¨²squeda de Similitud Secuencial

> **PARA PENSAR ??:** Ingres¨¢ al servidor del NCBI y mir¨¢ los distintos programas derivados del BLAST que se ofrecen ?Para qu¨¦ sirve cada uno? ?En qu¨¦ casos usar¨ªas cada uno?

---

- **blastp (protein-protein BLAST):** Compara una secuencia de amino¨¢cidos contra una base de datos de prote¨ªnas.
  - **Caso de uso:** Encontrar hom¨®logos de una prote¨ªna, predecir su funci¨®n o buscar miembros de una familia de prote¨ªnas.

- **blastn (nucleotide-nucleotide BLAST):** Compara una secuencia de ADN/ARN contra una base de datos de nucle¨®tidos.
  - **Caso de uso:** Encontrar d¨®nde se localiza un gen en un genoma, buscar secuencias de ARN ribos¨®mico para identificaci¨®n taxon¨®mica o encontrar genes similares en otras especies.

- **blastx (translated nucleotide-protein BLAST):** Toma una secuencia de nucle¨®tidos, la traduce en los 6 marcos de lectura posibles y compara esas traducciones contra una base de datos de prote¨ªnas.
  - **Caso de uso:** Evaluar fragmentos de ADN de car¨¢cter codificante desconocido para determinar similitudes con prote¨ªnas e identificar nuevos genes.

- **tblastn (protein-translated nucleotide BLAST):** Toma una secuencia de prote¨ªna y la compara contra una base de datos de nucle¨®tidos que ha sido traducida din¨¢micamente en los 6 marcos de lectura.
  - **Caso de uso:** Localizar el gen espec¨ªfico que codifica una prote¨ªna determinada dentro de un genoma que carece de anotaci¨®n previa.

- **tblastx (translated nucleotide-translated nucleotide BLAST):** Compara las 6 traducciones de una secuencia de nucle¨®tidos contra las 6 traducciones de una base de datos de nucle¨®tidos.
  - **Caso de uso:** Encontrar relaciones muy distantes entre secuencias de nucle¨®tidos que no se pueden detectar de otra manera.

---

## Desaf¨ªo 7

*Nota: la herramienta me permite fijar un m¨¢ximo de 5000 "max target sequences".*

### E-value vs. % Identidad
El **E-value** es la probabilidad de que el parecido de las secuencias sea pura coincidencia o un error al azar, por eso buscamos que sea lo m¨¢s cercano a cero posible. El **% de identidad** es qu¨¦ tan parecidas son las secuencias. Si dos secuencias son muy parecidas (alto % de identidad), la probabilidad de que sea por error es casi cero (E-value bajo). A mayor parecido, menor es el E-value.

### Score vs. % Identidad
El **Score** funciona como el puntaje de un juego donde cada letra que coincide exactamente suma puntos y las que no coinciden restan. Entonces, si la secuencia encontrada tiene muchas letras iguales a la dada (alto % de identidad), el sistema le otorgar¨¢ un puntaje (score) mucho m¨¢s alto. M¨¢s parecido es igual a m¨¢s puntos.

### Score vs. E-value
Uniendo las otras dos ideas, si un alineamiento logr¨® acumular muchos puntos (Score alto) porque las secuencias coinciden muy bien, la probabilidad de que ese resultado sea una simple coincidencia al azar es casi nula (E-value muy cercano a cero). A mayor puntaje de Score, m¨¢s bajo y confiable es el E-value.

---

## Desaf¨ªo 8

La longitud de la secuencia es fundamental para el valor estad¨ªstico. A mayor longitud de la secuencia de entrada (query), m¨¢s informaci¨®n tiene el algoritmo para distinguir entre una verdadera relaci¨®n evolutiva (homolog¨ªa) y una coincidencia al azar.

Las secuencias cortas tienen menor poder discriminatorio. Cuando una secuencia es muy peque?a, es dif¨ªcil acumular suficiente puntaje (score), lo que hace que los E-values sean altos y no se pueda asegurar si los resultados encontrados son realmente parientes evolutivos o simple ruido estad¨ªstico.
