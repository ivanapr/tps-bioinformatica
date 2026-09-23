# Respuestas a los Desafíos de Biomoléculas

### DESAFÍO I: ¿Podrías buscar un ejemplo de macromoléculas que almacenen información sobre la ‘identidad’ de un organismo dado?

**Respuesta:** La macromolécula clave es el **Ácido Nucleico**, y más específicamente, el **ADN (ácido desoxirribonucleico)**. Funciona como el "código fuente" o el disco duro biológico que almacena toda la información genética que define a un ser vivo.

---

### DESAFÍO II: Proponé una forma de expresar la información contenida en la estructura primaria de las proteínas usando tipos de datos de los lenguajes de programación que conocés.

**Respuesta:** La forma más simple y directa es usar un **`string` (cadena de texto)** porque la estructura primaria es una secuencia de aminoácidos representados por letras.

*   **Ejemplo:** `proteina = "MLPGLALLLLAAWTARALEVPTQ"`

---

### DESAFÍO III: ¿En qué tipo de datos podrías expresar la información de la estructura terciaria proteica?

**Respuesta:** Un string no alcanza porque necesitamos guardar la posición 3D. La mejor forma es usar una **lista o un array de objetos (o diccionarios)**. Cada objeto representaría un átomo y tendría propiedades para sus **coordenadas `x`, `y`, `z`**.

*   **Ejemplo de estructura:** `[ {"atomo": "N", "x": 1.2, "y": 0.5, "z": 3.4}, {"atomo": "C", ...}, ... ]`

---

### DESAFÍO IV: Rosalind Franklin es una científica muy relevante, que tuvo menos reconocimiento del merecido. ¿Cuáles fueron sus contribuciones en este campo? ¿Qué nos cuenta su historia acerca del mundo de la ciencia?

**Respuesta:**
*   **Contribución:** Su aporte crucial fue la **"Fotografía 51"**, una imagen obtenida por difracción de rayos X que fue la evidencia experimental definitiva para demostrar que la estructura del ADN era una doble hélice.
*   **Lección de su historia:** Su caso expone la histórica falta de reconocimiento hacia las mujeres en la ciencia, ya que sus datos fueron fundamentales para el modelo de Watson y Crick, pero ella no recibió el crédito merecido en su momento.

---

### DESAFÍO V: Escribí un scrip en Python que prediga la estructura secundaria que adoptará cada residuo (aminoácido) de la secuencia proteica dada, especificandola como H (si es una hélice), B (si es una hoja beta plegada) y L (si es un bucle o loop).

**Respuesta:** 
```
# Usamos solo los 3 aminoácidos del ejemplo original con valores inventados.
propensiones = {
    'A': {'H': 1.42, 'B': 0.83, 'L': 0.66},  # Alanina prefiere Hélice
    'V': {'H': 1.06, 'B': 1.70, 'L': 0.50},  # Valina prefiere Hoja Beta
    'G': {'H': 0.57, 'B': 0.75, 'L': 1.56},  # Glicina prefiere Bucle (Loop)
}

def predecir_estructura_simple(secuencia, propensiones):
    """
    Predice la estructura secundaria de una proteína de forma simple,
    basándose en la propensión de cada aminoácido individual.
    """
    prediccion = ""
    for aminoacido in secuencia.upper():
        if aminoacido in propensiones:
            # Busca la estructura ('H', 'B', 'L') con el valor más alto
            mejor_estructura = max(propensiones[aminoacido], key=propensiones[aminoacido].get)
            prediccion += mejor_estructura
        else:
            prediccion += '?'  # Si el aminoácido no está en nuestra tabla
    return prediccion

# --- Ejemplo de uso original ---
secuencia_proteica = "AVG"
prediccion_final = predecir_estructura_simple(secuencia_proteica, propensiones)

print(f"Secuencia de entrada: {secuencia_proteica}")
print(f"Predicción de estructura: {prediccion_final}") 
# Según la tabla: A -> H, V -> B, G -> L
# Resultado esperado: HBL
```

---

### DESAFÍO VI: ¿Qué hace distintos a dos individuos de una especie? Propone una forma de corroborar tu respuesta realizando un diagrama de un posible método computacional.

**Respuesta:**
*   **Qué los hace distintos:** Las **variaciones en la secuencia de su ADN**. Pequeños cambios en el "código" genético son la base de las diferencias individuales.
*   **Método computacional para corroborarlo:** El proceso se conoce como **alineamiento de secuencias**.
    1.  **Input:** Se cargan las dos secuencias de ADN a comparar.
    2.  **Proceso:** Un algoritmo las superpone y las recorre carácter por carácter.
    3.  **Output:** El programa reporta todas las posiciones donde encuentra diferencias entre las dos secuencias.
