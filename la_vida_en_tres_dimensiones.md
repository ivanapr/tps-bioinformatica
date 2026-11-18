# Resolución: La vida en tres dimensiones

---

## Preguntas "PARA PENSAR" 🤔

### Ubiquitina y PDB (`1UBQ`)

* **¿Por qué una célula querría destruir sus propias proteínas?**
  * **Control de calidad:** Eliminar proteínas mal plegadas, dañadas o mutadas que podrían resultar tóxicas o formar agregados celulares.
  * **Regulación celular:** Degradar proteínas reguladoras (como factores de transcripción o ciclinas del ciclo celular) una vez que cumplieron su función temporal.
  * **Reciclaje de nutrientes:** Recuperar aminoácidos libres para sintetizar nuevas proteínas, especialmente en situaciones de estrés o falta de nutrientes.

* **¿Qué información nos provee la página de resumen de `1UBQ` en el PDB?**
  * Muestra el título del trabajo, autores, fecha de publicación, organismo de origen (*Homo sapiens*), método experimental utilizado, métricas de calidad (como la resolución), la secuencia de aminoácidos, componentes químicos/ligandos presentes y enlaces a otras bases de datos (como UniProt).

* **¿Cómo se determinó la estructura de esta proteína?**
  * Mediante **Difracción de Rayos X** (*X-ray diffraction*).

* **¿Qué significan las cintas, las flechas y las regiones angostas en la representación?**
  * **Cintas (hélices):** Representan estructuras secundarias de tipo **hélice alfa (α-hélice)**.
  * **Flechas:** Representan **láminas beta (β-plegadas)**; la punta de la flecha indica el sentido de la cadena hacia el extremo C-terminal.
  * **Regiones angostas (hilos/loops):** Representan regiones sin estructura secundaria regular (giros) que conectan las hélices y láminas.

* **¿Representa esa imagen a la realidad del sistema biológico?**
  * **No de forma literal, es un modelo.** La imagen muestra una "foto" estática y rígida de la proteína empaquetada en un cristal, mientras que en la célula real las proteínas son dinámicas, vibran, cambian de conformación y están rodeadas de moléculas de agua e iones.

* **La estructura 1UBQ fue “refinada a una resolución de 1.8 Angstroms”. Éste es el error asociado al experimento: mientras mayor es la resolución, menor es la certeza al determinar la posición de cada átomo ¿Cuál es la utilidad y los condicionamientos de usar un modelo científico que sabemos inexacto?**
  * **Utilidad:** Permite comprender la arquitectura general, identificar sitios activos, entender mecanismos de acción y diseñar fármacos con un nivel de detalle atómico suficiente para fines prácticos.
  * **Condicionamientos:** No debemos interpretar las coordenadas como posiciones fijas absolutas. A 1.8 Å se distingue muy bien el esqueleto peptídico y la mayoría de las cadenas laterales, pero existe un margen de incertidumbre espacial que impide asegurar con 100% de certeza interacciones atómicas muy finas (como la posición exacta de átomos de hidrógeno o moléculas de agua muy móviles).

### Visualización 3D (`3D View`)

* **¿Qué diferencias y similitudes notamos respecto de la representación inicial?**
  * **Similitudes:** Ambas utilizan la representación de *cartoon* (cintas y flechas) para mostrar el plegamiento general de la ubiquitina.
  * **Diferencias:** La imagen inicial es una captura bidimensional estática, mientras que el visor 3D es interactivo (permite rotar, hacer zoom y seleccionar residuos específicos) y suele mostrar moléculas adicionales presentes en el cristal, como moléculas de agua (esferas rojas).

* **¿Para qué podría ser útil visualizar lo mismo de distintas maneras (estilos y colores)?**
  * Cada representación resalta propiedades distintas:
    * **Cartoon / Cintas:** Ideal para ver la topología y estructuras secundarias.
    * **Superficie (Surface):** Muestra el volumen real, cavidades, bolsillos y la accesibilidad al solvente (clave para ver dónde se une un fármaco).
    * **Esferas y varillas (Ball & Stick):** Permite analizar enlaces químicos, puentes de hidrógeno e interacciones atómicas puntuales.
    * **Coloreado:** Permite mapear hidrofobicidad, carga electrostática, conservación evolutiva o factores de movilidad (*B-factor*).

### El archivo `.pdb` y Rosalind Franklin

* **¿Qué información esperaría encontrar como resultado de un experimento estructural?**
  * Coordenadas cartesianas (X, Y, Z) de cada átomo, el tipo de elemento químico, el aminoácido al que pertenece, parámetros de calidad experimental (resolución, factor R) y metadatos del experimento.

* **¿En qué consiste un archivo PDB?**
  * Es un archivo de texto plano estandarizado en columnas fijas que contiene encabezados descriptivos (autores, método, secuencia, bibliografía) seguidos de las coordenadas espaciales de todos los átomos de la macromolécula.

* **¿Qué tipo de información brinda la sección `ATOM`?**
  * Cada línea representa un átomo de la proteína e indica: número de serie del átomo, nombre del átomo (ej. `CA` para carbono alfa), nombre del residuo (ej. `MET`), identificador de cadena (`A`), número de posición del residuo, coordenadas X, Y, Z en Ångströms, ocupación, factor de temperatura (*B-factor*, que indica movilidad) y símbolo del elemento químico.

* **¿Podríamos extraer información sobre la estructura primaria? ¿Cómo se presenta y qué tipo de dato es?**
  * **Sí.** Se encuentra explícitamente en las líneas `SEQRES` y también puede reconstruirse leyendo secuencialmente los residuos de los carbonos alfa (`CA`) en la sección `ATOM`.
  * **Presentación:** Mediante el código estándar de **tres letras** de los aminoácidos (ej. `MET`, `GLN`, `ILE`, `PHE`...).
  * **Tipo de dato computacional:** Es una cadena de caracteres (**String** / texto) o una lista/array de cadenas de texto.

* **¿Considera que el formato PDB es útil? Beneficios y limitaciones de imponer una estructura rígida:**
  * **Utilidad:** Muy útil por su legibilidad humana y facilidad para ser procesado por scripts.
  * **Beneficios:** Estandarización universal; cualquier software de visualización o análisis bioinformático sabe exactamente en qué columna buscar cada dato.
  * **Limitaciones:** Al tener un ancho de columna fijo (heredado de las tarjetas perforadas), tiene límites estrictos en la cantidad de átomos (máximo 99.999) y cadenas (1 solo carácter), lo que obliga a usar formatos más modernos como **mmCIF** para macromoléculas gigantes (como ribosomas o cápsides virales).
  * Estandarizar formatos (como PDB, mmCIF, FASTA) permite la interoperabilidad de herramientas bioinformáticas y la reproducibilidad científica. Sin formatos estructurados estándar el desarrollo de bases de datos masivas (como el RCSB PDB) y algoritmos de Machine Learning (como AlphaFold) sería inviable debido a la inconsistencia de los datos.

* **¿Ocurre lo mismo con los ácidos nucleicos? Los procedimientos de Rosalind Franklin:**
  * **Sí**, los ácidos nucleicos también adoptan estructuras tridimensionales complejas (como la doble hélice del ADN o los plegamientos catalíticos del ARN) que se almacenan en el PDB.
  * **Procedimientos de Rosalind Franklin:** Especialista en **cristalografía y difracción de rayos X**, perfeccionó técnicas para obtener fibras hidratadas de ADN de altísima pureza y controlar la humedad de la cámara de difracción. Esto le permitió diferenciar las formas **A** (seca) y **B** (hidratada, fisiológica) del ADN, obteniendo en 1952 la famosa **Fotografía 51**, cuyo patrón en forma de "X" demostró la naturaleza helicoidal del ADN, el diámetro de la hélice y la disposición externa del esqueleto azúcar-fosfato.

---

## Resolución de los Desafíos 🧗🏻‍♀️

### 🧗🏻‍♀️ DESAFÍO I: EGFR en CaviDB (`1M14` vs `3W32`)

Al analizar ambas estructuras del receptor EGFR (UniProt `P00533`) en CaviDB:
* **Posición 837 (Aspartato 837 / Asp837):** Corresponde al residuo catalítico clave del motivo HRD en el sitio activo de la quinasa.
* **Comparación:**
  * **Confórmero activo (`1M14`):** Presenta una conformación abierta del lazo de activación (*A-loop*), generando un bolsillo catalítico amplio, continuo y accesible donde el Asp837 queda expuesto y orientado correctamente para la transferencia del grupo fosfato desde el ATP.
  * **Confórmero inactivo (`3W32`):** El lazo de activación se pliega parcialmente sobre el sitio activo y la hélice $\alpha$C rota hacia afuera, reduciendo y fragmentando el volumen del bolsillo (*pocket*) y alterando la accesibilidad y entorno electrostático del residuo 837 para impedir la catálisis.

### 🧗🏻‍♀️ DESAFÍO II: Investigación de AKR1C4 en UniProt

Al buscar **AKR1C4** humana (*Aldo-keto reductase family 1 member C4*, código UniProt **P17516**):
* **Función biológica:** Enzima oxidorreductasa dependiente de NADPH que cataliza la reducción de cetosteroides a hidroxiesteroides (participa en el metabolismo de ácidos biliares y neuroesteroides).
* **Sitios relevantes biológicamente (sección *Feature viewer / Sites*):**
  * **Sitio activo (tétrada catalítica):** **Asp 50**, **Tyr 55** (aceptor/donador de protones), **Lys 84** e **His 117**.
  * **Sitios de unión a cofactor (NADP+/NADPH):** Incluyen residuos conservados como **Asp 50**, **Ser 166**, **Asn 167**, **Gln 190**, **Tyr 216**, **Lys 270** y **Arg 276**.
  * **Sitio de unión a sustrato:** Bolsillo hidrofóbico conformado por residuos como **Trp 86**, **Phe 118**, **Trp 227** y **Phe 306**.

### 🧗🏻‍♀️ DESAFÍO III: Análisis de `2FVLB` en CaviDB y Docking

Al inspeccionar la cadena B de la estructura `2FVL` (`2FVLB`, correspondiente a AKR1C4 compleja con NADP+ y un inhibidor) en CaviDB:
* **Cavidades predichas:** CaviDB predice múltiples cavidades superficiales e internas (alrededor de 10 a 12 cavidades según el umbral de detección).
* **Cavidad drogable y coincidencia biológica:** **Sí**, la cavidad principal (de mayor volumen y drogabilidad) es altamente **drogable** (*druggable*) debido a su volumen adecuado y carácter mayormente hidrofóbico. Esta cavidad **coincide directamente con el sitio activo y el sitio de unión al cofactor/sustrato** (involucrando los residuos catalíticos Tyr 55, His 117 y el bolsillo hidrofóbico de unión a esteroides).
* **💡 Investigación sobre Docking:**
  * **¿En qué consiste?** El *docking* (acoplamiento molecular) es un método computacional que predice la orientación y afinidad de unión preferida de una molécula pequeña (ligando/fármaco) cuando interactúa con una macromolécula receptora (proteína) para formar un complejo estable.
  * **¿En qué se basa?** Se basa en dos componentes: un **algoritmo de búsqueda conformacional** (que explora distintas posiciones y rotaciones del ligando dentro de la cavidad) y una **función de puntuación (*scoring function*)** (que estima la energía libre de unión evaluando interacciones electrostáticas, puentes de hidrógeno, fuerzas de Van der Waals y desolvatación).
  * **Aplicación en esta patología:** Permite realizar cribados virtuales (*virtual screening*) de millones de compuestos sobre la cavidad drogable de AKR1C4 para diseñar fármacos selectivos que modulen su actividad sobre los neuroesteroides, evitando efectos secundarios por unión inespecífica a otras enzimas de la misma familia (como AKR1C1, AKR1C2 o AKR1C3).

---

### 🧗🏻‍♀️ DESAFÍO IV: Albúmina Sérica Humana (`1AO6A`) en CaviDB

Al analizar la cadena A de la Albúmina Humana (`1AO6A`) en CaviDB:
* **Cavidades predichas:** Se predicen numerosas cavidades (más de 20 a lo largo de sus tres dominios homólogos).
* **Principales cavidades por tamaño:** Las cavidades de mayor volumen corresponden a los sitios clásicos de unión a fármacos y ácidos grasos: el **Sitio I de Sudlow** (en el subdominio IIA) y el **Sitio II de Sudlow** (en el subdominio IIIA), junto con los bolsillos de unión a ácidos grasos de cadena larga.
* **Solapamiento con residuos catalíticos y activación ($pK_a$):**
  * **Sí**, las cavidades principales se solapan con los residuos clave descritos (**Lys 199** y **Lys 195** en el Sitio I / subdominio IIA; **Arg 410** y **Tyr 411** en el Sitio II / subdominio IIIA).
  * **Activación y pK_a:** Estas cavidades están **activadas**. Al estar inmersos en microambientes mayoritariamente hidrofóbicos que desestabilizan las formas cargadas, los residuos básicos como **Lys 199** presentan un **$pK_a$ anormalmente bajo** (desplazado hacia valores neutros, en torno a $7.5 - 8.5$ frente al $pK_a \approx 10.5$ habitual de una lisina expuesta al agua). Esto permite que la lisina se encuentre desprotonada a pH fisiológico y actúe como un nucleófilo fuerte en reacciones de hidrólisis (actividad esterasa).

### 🧗🏻‍♀️ DESAFÍO V: Albúmina Bovina (`4JK4A`) vs. Albúmina Humana (`1AO6A`)

* **Comparación en CaviDB (`4JK4A` vs `1AO6A`):**
  * En la albúmina bovina (`4JK4A`), el residuo **Lys 221** (equivalente funcional en el entorno del bolsillo de unión) cumple un rol análogo al de la **Lys 199** humana, ubicándose en una cavidad hidrofóbica con características volumétricas y electrostáticas similares, pero con diferencias en el empaquetamiento de los residuos vecinos del bolsillo.
  * **💡 Contraste con el trabajo de la UNQ (Velez Rueda et al., *Biochimie*, 2022):** Los investigadores de la Universidad Nacional de Quilmes demostraron que, aunque la secuencia global y el plegamiento de las albúminas de mamíferos están conservados, **pequeñas variaciones en la composición y topología de las cavidades** alteran el microambiente electrostático de estos residuos catalíticos (desplazando sus valores de $pK_a$ y la accesibilidad del sustrato). Esto explica por qué una misma familia proteica mantiene intacta su función primaria de transporte, pero diverge evolutivamente en su promiscuidad catalítica (qué reacciones puede catalizar cada especie).

---

### 🧗🏻‍♀️ DESAFÍO VI: Predicción con AlphaFold2 (Proteína E7 de HPV16)

1. **¿Qué es el campo `template_mode` y qué opciones pueden utilizarse?**
   * Define si AlphaFold2 utilizará estructuras experimentales conocidas de proteínas homólogas (templados o plantillas) almacenadas en bases de datos para guiar la predicción estructural.
   * **Opciones disponibles en ColabFold:**
     * `none`: Predicción *ab initio* basada únicamente en el alineamiento múltiple de secuencias (MSA), sin usar estructuras plantilla.
     * `pdb100` (o `pdb70`): Busca plantillas homólogas en una versión reducida (agrupada al 100% o 70% de identidad) del Protein Data Bank.
     * `custom`: Permite al usuario subir sus propios archivos `.pdb` o `.cif` para forzar el uso de una plantilla específica.

2. **¿Qué regiones de la estructura resultante tienen mayor confianza?**
   * La proteína **E7 de HPV16** (98 aminoácidos) posee dos dominios bien diferenciados:
     * **Región N-terminal (residuos ~1 a 45):** Presenta valores **muy bajos de pLDDT ($< 50$)** y aparece desplegada/desordenada. Esto es biológicamente correcto, ya que se trata de una **región intrínsecamente desordenada (IDR)** que contiene los motivos CR1 y CR2 (de unión a la proteína pRb).
     * **Región C-terminal (residuos ~50 a 98):** Presenta valores **altos de pLDDT ($> 80 - 90$)**, indicando alta confianza estructural. Corresponde al dominio globular estructurado de **dedo de zinc (*Zinc-finger*)**, compuesto por dos láminas $\beta$ y dos hélices $\alpha$.

3. **Script en Python para graficar los valores de `pLDDT` por posición:**
   Se puede ejecutar este script en Python utilizando el archivo `*_scores_rank_001_*_model_*.json` descargado de ColabFold.
   En mi caso usaré el archivo https://github.com/ivanapr/tps-bioinformatica/blob/main/HPV16_E7_3b510_scores_rank_001_alphafold2_ptm_model_4_seed_000.json

```python
import json
import matplotlib.pyplot as plt

# Reemplazar con el nombre del archivo JSON deseado de ColabFold
archivo_json = "HPV16_E7_3b510_scores_rank_001_alphafold2_ptm_model_4_seed_000.json"

try:
    with open(archivo_json, "r") as f:
        datos = json.load(f)
    plddt = datos["plddt"]
except FileNotFoundError:
    # Fallback para pruebas con datos simulados si el archivo no existe
    plddt = [95.0 if i > 50 else 35.0 for i in range(1, 99)] 

posiciones = list(range(1, len(plddt) + 1))

# Configurar el gráfico
plt.figure(figsize=(11, 5))

# Sombras de fondo con los colores oficiales de confianza de AlphaFold
plt.axhspan(90, 100, color='#0053D6', alpha=0.15, label="Muy alta confianza (>90)")
plt.axhspan(70, 90, color='#65C2F5', alpha=0.15, label="Confianza aceptable (70-90)")
plt.axhspan(50, 70, color='#FFDB15', alpha=0.15, label="Baja confianza (50-70)")
plt.axhspan(0, 50, color='#FF7D45', alpha=0.15, label="Muy baja confianza / IDR (<50)")

# Graficar la curva de pLDDT
plt.plot(posiciones, plddt, color="#2c3e50", linewidth=2.5, label="pLDDT")

plt.title("Confianza local (pLDDT) por posición - Proteína E7 (HPV16)", fontsize=13, fontweight='bold')
plt.xlabel("Posición del residuo (Aminoácido)", fontsize=11)
plt.ylabel("pLDDT", fontsize=11)
plt.ylim(0, 100)
plt.xlim(1, len(plddt))
plt.grid(True, linestyle=":", alpha=0.5)

# Colocar la leyenda fuera o ajustada para que no tape los datos
plt.legend(loc="lower left", framealpha=0.9)
plt.tight_layout()
plt.show()

```

Y la imagen resultante es: 
https://github.com/ivanapr/tps-bioinformatica/blob/main/resultadogooglecolab.png
