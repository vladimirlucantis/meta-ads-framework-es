# Estrategias de campaña en Meta Ads

Este skill no asume una sola forma de estructurar campañas. Diferentes consultores y negocios usan distintas estrategias según el mercado, el presupuesto y el tipo de producto. Antes de diagnosticar una cuenta, identificar qué estrategia está ejecutando el usuario.

## Las 5 estrategias más comunes

### 1. Advantage+ puro (dejar decidir al algoritmo)

Meta decide audiencia, ubicaciones y creativos. El media buyer solo sube los activos.

**Cuándo se usa:**

- E-commerce con catálogo amplio (Advantage+ Shopping Campaigns)
- Cuentas con alto volumen histórico de datos (50+ eventos semanales)
- Negocios que no tienen una audiencia nicho clara

**Señales de que el usuario usa esta estrategia:**

- Ad sets con nombre "Advantage+" o "AAC"
- Pocos ad sets activos (1 o 2 total)
- Sin segmentación manual por interés
- Audiencias "amplias" en vez de públicos específicos

**Umbrales típicos:**

- Frecuencia tolerable más alta (hasta 2.5) porque rota audiencia sola
- Necesita más tiempo de aprendizaje (10-14 días vs 7)
- El CPM tiende a ser más bajo (Meta optimiza entrega)

**Cómo diagnosticar:**

- No dividir el análisis por "tipo de audiencia"
- Medir performance total de la campaña
- Si el costo/conv es aceptable, mantener sin intervenir
- Rotar creativos cuando la frecuencia supera el umbral

---

### 2. Segmentación por intereses + exclusiones (CBO/ABO manual)

El media buyer define manualmente audiencias por intereses, comportamientos o lookalikes. Típicamente múltiples ad sets, cada uno con un interés o cluster distinto.

**Cuándo se usa:**

- Cuentas chicas (USD 50-500) donde el testing granular ayuda
- Negocios con audiencia muy específica (ej: médicos, jugadores de ajedrez)
- Cuando hay hipótesis claras de segmentación a probar

**Señales:**

- Ad sets nombrados por interés: "Yoga", "Cocina", "Emprendedores"
- 3 a 8 ad sets activos en paralelo
- Cada ad set con 1-3 intereses explícitos
- Uso de exclusiones (web visitors, clientes existentes)

**Umbrales típicos:**

- Frecuencia normal (< 2.0)
- Período de aprendizaje estándar (7 días)
- Cada ad set necesita mínimo USD 5-10/día para no morir de hambre

**Cómo diagnosticar:**

- Comparar performance entre ad sets (cuál interés funciona mejor)
- Pausar ad sets perdedores después de 7 días con gasto suficiente
- Escalar el ganador un 20% cada semana

---

### 3. FRIA + CALIENTE (prospecting + retargeting)

Separación explícita entre audiencia que no conoce el negocio (FRIA) y audiencia que ya tuvo contacto (CALIENTE). Dos ad sets mínimo, cada uno con creativos y copy distintos.

**Cuándo se usa:**

- Negocios con flujo constante de tráfico web o engagement social
- Cuentas con más de 3 meses de historia (suficiente audiencia CALIENTE)
- Cuando la oferta requiere varios toques antes de conversión

**Señales:**

- Ad sets nombrados "FRIO/FRIA" y "CALIENTE" (o "TOF"/"BOF", "Prospecting"/"Retargeting")
- Exclusiones explícitas en FRIA (visitors últimos 30-180 días, engagers)
- CALIENTE usa audiencias personalizadas (web, IG engagers, video viewers)
- Creativos distintos en cada ad set

**Umbrales típicos:**

- Frecuencia FRIA < 2.0, CALIENTE < 3.0 (más tolerancia porque es audiencia menor)
- CALIENTE debería convertir más barato que FRIA (si no, hay fatiga)
- CTR más alto en CALIENTE por intención

**Cómo diagnosticar:**

- NO comparar CPM ni costo/conv entre FRIA y CALIENTE directamente
- Cada uno se evalúa contra su propio umbral
- Si CALIENTE está más cara que FRIA, señal clara de fatiga creativa en retargeting

---

### 4. Creative testing (múltiples creativos bajo un solo ad set)

Un único ad set con audiencia amplia, donde se testean 3-6 creativos distintos para identificar cuál convierte mejor. Meta distribuye el presupuesto entre ellos.

**Cuándo se usa:**

- Fase temprana de una cuenta (antes de saber qué mensaje funciona)
- Después de filmar una tanda nueva de Reels
- Cuando hay dudas sobre hook, formato o ángulo

**Señales:**

- 1 ad set activo con 3+ ads adentro
- Nombres de ads descriptivos: "Hook dolor", "Hook solución", "Testimonio", "Producto"
- Presupuesto moderado (USD 10-30/día)
- Duración acotada (7-14 días de test)

**Umbrales típicos:**

- Mínimo 5 conversiones por ad antes de sacar conclusiones
- Si un ad llega a 0 conv con gasto equivalente a 3 conversiones del promedio, pausar
- El ganador queda; los perdedores se archivan; se testea nueva tanda

**Cómo diagnosticar:**

- Rankear ads por costo/conv dentro del ad set
- Recomendar pausar los 3x peores y escalar el mejor a su propio ad set
- No comparar ads hasta que cada uno tenga data suficiente

---

### 5. Conversion API + WhatsApp (negocios que no venden en sitio web)

Negocio donde la conversión principal ocurre fuera del sitio (mensaje de WhatsApp, llamada telefónica, visita presencial). El pixel no registra la conversión real. Se optimiza con eventos proxy o con objetivo "Mensajes".

**Cuándo se usa:**

- Servicios profesionales (abogados, psicólogos, contadores, consultores)
- Ventas por catálogo no integrado a sitio web
- Talleres, cursos y eventos que se venden por conversación
- Muchos negocios locales y de servicios en LATAM

**Señales:**

- Objetivo de campaña: "Conversaciones" (Mensajes)
- Botón de CTA "Enviar mensaje por WhatsApp"
- Pixel instalado pero con eventos que no corresponden a la venta real
- Pocas o cero conversiones registradas en pixel a pesar de tener clientes nuevos

**Umbrales típicos:**

- Se mide por costo por conversación, no por compra
- Excelente: < USD 0.35/conv (mensajes)
- Aceptable: USD 0.35 a USD 0.65
- Pausar: > USD 1.00

**Cómo diagnosticar:**

- Explicar al usuario que el pixel no va a optimizar hacia compradores reales
- Recomendar audiencia personalizada de clientes (mínimo 100 contactos) para lookalike
- Recomendar upload de conversiones offline si el volumen lo justifica
- Evaluar tasa de conversación-a-venta (fuera del Ads Manager) para calcular CPA real

---

## Cómo detectar qué estrategia usa el usuario

### Opción 1: Preguntar directamente

Si el usuario solo comparte métricas sin contexto, preguntar primero:

> "Antes de analizar, contame cómo estructurás la campaña. ¿Usás Advantage+, segmentación por intereses, FRIA+CALIENTE, creative testing, o alguna mezcla?"

### Opción 2: Inferir de los datos

Señales en el informe que indican la estrategia:

| Señal | Estrategia probable |
|---|---|
| 1-2 ad sets total, nombre "Advantage+" | Advantage+ puro |
| 3+ ad sets con nombres de intereses | Segmentación manual |
| Ad sets "FRIO"/"CALIENTE" | Prospecting + Retargeting |
| 1 ad set con 4+ ads | Creative testing |
| Objetivo "Mensajes" + WhatsApp | Conversion API/WhatsApp |

### Opción 3: No asumir

Si los nombres de ad sets son ambiguos, pedir clarificación antes de sacar conclusiones. Mejor preguntar que recomendar en base a una suposición errada.

---

## Mezclas y casos especiales

**Híbridas**: muchas cuentas combinan estrategias. Ejemplo común: 1 ad set Advantage+ para prospecting + 1 ad set CALIENTE manual para retargeting. Tratar cada ad set según su estrategia individual.

**Transiciones**: si un usuario viene de segmentación manual y está probando Advantage+ por primera vez, esperar más tiempo antes de comparar (Advantage+ necesita 10-14 días vs 7).

**Cuentas sin estrategia clara**: señal de oportunidad. Antes de diagnosticar, ayudar al usuario a definir una estrategia coherente.

---

## Qué NO hacer

- No asumir que FRIA+CALIENTE es la estrategia correcta para todos
- No criticar Advantage+ solo porque "deja decidir al algoritmo" (a veces es la mejor opción)
- No recomendar cambios de estrategia sin entender el contexto (volumen, tipo de negocio, historia)
- No aplicar umbrales de una estrategia a otra (ej: frecuencia 2.0 no aplica igual en Advantage+)
