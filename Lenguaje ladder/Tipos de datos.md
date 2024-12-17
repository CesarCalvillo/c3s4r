# Tipos de Datos en Lenguaje Ladder 📋

El lenguaje **Ladder** utilizado en los PLCs requiere el uso de diversos tipos de datos para representar las entradas, salidas, estados y variables internas. Estos tipos de datos varían según el fabricante del PLC, pero los más comunes se describen a continuación:

---

## 🔢 Tipos de Datos Comunes

### 1. **Bool (Booleano)**
- Representa un valor lógico: `Verdadero (1)` o `Falso (0)`.
- Usado principalmente para:
  - Entradas digitales (botones, sensores).
  - Salidas digitales (relés, lámparas).
  - Condiciones lógicas en contactos y bobinas.

**Ejemplo:**
```ladder
| Start Button |  Motor Output
     | |-------------( )
```

### 2. **Int (Entero)**
- Representa números enteros, positivos o negativos, generalmente de 16 bits.
- Usado para:
  - Contadores (CTU, CTD).
  - Temporizadores (TON, TOF).
  - Variables internas.

**Ejemplo:**
```ladder
| Counter Input |    Counter (C1)
     | |-------------(CTU)
```

### 3. **DInt (Entero Doble)**
- Enteros de 32 bits, utilizados para manejar valores más grandes.
- Común en aplicaciones que requieren mayor precisión o rangos extensos.

### 4. **Real (Flotante)**
- Representa números con punto decimal (32 bits).
- Usado en cálculos matemáticos y aplicaciones que requieren mayor precisión, como sensores analógicos (temperatura, presión, etc.).

**Ejemplo:**
```ladder
| Analog Input |   Temperature
     | |-------------(MOV)
```

---

## 📋 Tipos de Datos Estructurados

### 1. **Timer (Temporizador)**
- Usado para medir intervalos de tiempo.
- Propiedades principales:
  - `Preset (PRE)`: Tiempo predefinido.
  - `Accumulated (ACC)`: Tiempo acumulado.
  - `Done (DN)`: Indica que el tiempo ha expirado.

**Ejemplo:**
```ladder
| Start Button |    Timer (T1)
     | |-------------(TON)
```

### 2. **Counter (Contador)**
- Usado para contar eventos.
- Tipos:
  - **CTU:** Contador ascendente.
  - **CTD:** Contador descendente.
- Propiedades principales:
  - `Preset (PRE)`: Valor objetivo.
  - `Accumulated (ACC)`: Valor actual.

**Ejemplo:**
```ladder
| Sensor Input |    Counter (C1)
     | |-------------(CTU)
```

---

## 🔀 Tipos de Datos Especializados

### 1. **String (Cadena de Texto)**
- Almacena texto o caracteres.
- Usado en interfaces HMI y mensajes.

**Ejemplo:**
```ladder
| Alarm Trigger |   Display Message
     | |-------------(MOV "Alarma Activa")
```

### 2. **Array (Arreglo)**
- Conjunto de datos del mismo tipo.
- Usado para manejar múltiples entradas/salidas o datos en secuencia.

**Ejemplo:**
```ladder
| Process Step |   Array Index
     | |-------------(MOV Array[0])
```

---

## 🌐 Representación en Memoria

### Direccionamiento
- Cada tipo de dato se almacena en una dirección específica de la memoria del PLC.
- Ejemplo de etiquetas:
  - **I:** Entradas físicas.
  - **Q:** Salidas físicas.
  - **M:** Memoria interna.
  - **DB:** Bloques de datos.

**Ejemplo de asignaciones:**
- `I0.0`: Entrada digital.
- `Q0.1`: Salida digital.
- `M1.0`: Variable booleana.
- `DB1.DBD0`: Doble entero en un bloque de datos.

---

## 🛠️ Mejores Prácticas
1. Usa nombres descriptivos para las variables.
2. Selecciona el tipo de dato adecuado para optimizar el uso de memoria.
3. Documenta los rangos de valores y propósitos de cada variable.

---

El conocimiento de los tipos de datos en Ladder es esencial para desarrollar programas eficientes y funcionales en sistemas de automatización industrial. ¡Domínalos para llevar tus proyectos al siguiente nivel! 🚀

> 💡 *"Un tipo de dato correcto es la base de un programa bien diseñado."*
