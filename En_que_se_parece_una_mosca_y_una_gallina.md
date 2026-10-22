# Análisis Comparativo de Secuencias de Citocromo C

## Tabla de Especies y Secuencias

| Secuencia | Nombre taxonómico | Nombre común | 
| ----- | ----- | ----- | 
| `NP_061820.1` | *Homo sapiens* | Humano | 
| `NP_001072946.1` | *Gallus gallus* | Gallina | 
| `NP_001065289.1` | *Pan troglodytes* | Chimpancé | 
| `NP_001157486.1` | *Equus caballus* | Caballo | 
| `NP_001183974.1` | *Canis lupus familiaris* | Perro | 
| `AEP27192.1` | *Gorilla gorilla* | Gorila occidental | 
| `XP_024245566.1` | *Oncorhynchus tshawytscha* | Salmón real | 
| `NP_001086101.1` | *Xenopus laevis* | Rana de uñas africanas | 
| `NP_477164.1` | *Drosophila melanogaster* | Mosca de la fruta | 

### 🤔 ¿Cuán sencillo será alinear dos o más secuencias a mano? ¿Cuánto influirán el número de secuencias a alinear, su longitud, y la similitud entre ellas?
Poco sencillo. Mientras mayor sea la cantidad de secuencias y su longitud, más complejo se vuelve el proceso. Es más fácil alinear si tienen la misma longitud, y resulta más intuitivo a mayor similitud entre ellas.

### 🤔 ¿Son parecidos los citocromos c de humano y gallo?
Bastante parecidos. Solo tienen 13 aminoácidos distintos entre ellos y comparten el resto. Se observa una alta similitud visual en las secuencias.

### 🤔 ¿Qué teorías subyacen a este análisis?
La **teoría de la evolución** y el concepto de **ancestro común**.

* Por ejemplo, se utiliza la proteína citocromo c, fundamental para la respiración celular.
* Entre humano, chimpancé y gorila observamos secuencias idénticas.

### 🤔 ¿Cómo nos ayuda la evolución a explicar sus similitudes y diferencias?

* **Similitudes:** Se dan por el ancestro común como por ejemplo notamos entre humano, chimpancé y gorila que en especies más emparentadas la proteína se mantiene con menores cambios a diferencia de especies más lejanas como sería un gallo. Pero la cercanía se define gen a gen entonces los genes relacionados deberían ser menos propensos a cambio.
Se espera que procesos vitales para los organismos como la respiración celular conserven similitudes 
* **Diferencias:** Se dan por mutaciones y divergencias acumuladas en el ADN a lo largo del tiempo.

### 🤔 ¿Qué indican los colores?
Representan propiedades fisicoquímicas o estructurales deducidas de la secuencia de aminoácidos (como por ejemplo la polaridad, carga, etc.).

### 🤔 ¿Qué indican el guión (`-`), los dos puntos (`:`) y el asterisco (`*`)?

* **Guión (`-`):** Representa un *gap* (inserción o deleción).
* **Dos puntos (`:`):** Conservación de propiedades físico-químicas (variantes conservativas).
* **Asterisco (`*`):** Identidad absoluta (misma presencia de aminoácido en esa posición, la secuencia se conserva en bloque).

### 🤔 A simple vista, ¿se conserva la secuencia del citocromo c en los organismos?
Sí, se percibe claramente observando la cantidad de asteriscos, letras compartidas y alineación de colores entre las secuencias.

### 🤔 ¿Creeríamos que todos los organismos se asemejan por igual al resto, o se pueden identificar grupos de mayor similitud? Si es así, ¿tienen sentido?
No todos los organismos se asemejan por igual al resto, es verdad que se pueden identificar grupos de mayor similitud viendo el árbol resultante. Y las similitudes se dan por funciones vitales del producto génico, en este caso la respiración celular. Y también con la adaptación del organismo al medio.
Tiene sentido por la teoría de evolución porque no todos los grupos tienen necesariamente el mismo ancestro común pero no se fueron armando otros clados, falta información para sacar conclusiones sobre eso o sea más secuencias.
Este árbol que resultó en la herramienta no realiza el análisis correcto.

### 🤔 ¿Qué evidencias nos aportaría este análisis, a la luz de la evolución?
A mayor similitud en las secuencias, mayor cercanía filogenética y parentesco entre los organismos.

### 🤔 A juzgar por los organismos participantes, ¿cuáles creería que deberían estar más agrupados en el árbol filogenético?
Deberían estar más agrupados el humano con las demás especies de primates, seguidos por los otros mamíferos, mientras que el grupo más distante debería ser la mosca.

### 🤔 Observemos el árbol filogenético. ¿Concuerda con lo esperado? ¿De qué organismos son los citocromos c más parecidos? ¿Cómo se explica?
Sí, concuerda con lo esperado. Los citocromos c más parecidos son los del humano y los primates, lo cual se explica mediante la divergencia evolutiva.
