# Checklist de configuración de pixel y API de Conversiones

Guía práctica para verificar que el pixel está bien instalado, que la API de Conversiones está activa y que los eventos se disparan correctamente.

## 1. Pixel base instalado

### Verificar

Con el Facebook Pixel Helper (extensión de Chrome):

- Entrar al sitio web del negocio
- Abrir la extensión
- Debería mostrar el ID del pixel y el evento PageView disparándose

### Si no dispara

Causas comunes:

- El pixel no está instalado (revisar que el tag esté en todas las páginas)
- Ad blocker del navegador lo está bloqueando (probar en incógnito)
- El pixel está instalado pero el ID está mal (verificar que coincida con el del Administrador Comercial)

## 2. API de Conversiones activa

### Verificar

En Events Manager → Pixel → Resumen:

- Debería aparecer "Browser + Server" en la fila de eventos
- Si aparece solo "Browser", la API de Conversiones no está activa
- Si aparece solo "Server", falta el pixel del navegador

### Activación según stack

- **WooCommerce**: plugin oficial "Meta for WooCommerce" (configurar token de acceso)
- **Shopify**: integración nativa desde Shopify Admin → Sales channels → Facebook
- **Custom**: integración manual vía endpoint graph.facebook.com/v18.0/{pixel_id}/events

## 3. Deduplicación de eventos

### Problema frecuente

Cuando ambos disparan (browser + server) sin deduplicación, el mismo evento se cuenta 2 veces. Esto infla las métricas y confunde la optimización.

### Solución

Cada evento debe enviarse con un `event_id` único que coincida entre el browser event y el server event. Meta lo usa para deduplicar.

### Verificar

En Events Manager → Pruebas de eventos:

- Mirar la columna "Method" de cada evento reciente
- Si ves "Browser + Server" con el mismo event_id, está bien deduplicado
- Si ves dos filas separadas para el mismo evento, NO está deduplicando

## 4. Eventos clave según tipo de negocio

### E-commerce

- PageView (automático)
- ViewContent (producto individual)
- AddToCart
- InitiateCheckout
- Purchase (con valor y moneda)

### Lead generation

- PageView
- ViewContent (landing)
- Lead (formulario enviado)

### Negocio que convierte por WhatsApp

Acá el pixel NO puede optimizar hacia compradores reales porque la conversión ocurre fuera del sitio. Soluciones:

**Opción 1: Audiencia personalizada de clientes**

1. Exportar lista de clientes/suscriptores con nombre, apellido, teléfono, email
2. En Administrador Comercial → Audiencias → Crear audiencia personalizada → Lista de clientes
3. Subir archivo CSV (mínimo 100 contactos para que Meta lo acepte)
4. Esperar 24-48 horas a que se procese el matching
5. Usar esta audiencia para lookalike

**Opción 2: Conversión offline por carga manual**

1. En Events Manager → Conjuntos de datos offline
2. Crear conjunto nuevo
3. Subir CSV con teléfonos de los que convirtieron y fecha de conversión
4. Meta cruza contra la audiencia que vio ads y atribuye la conversión
5. Usar ese evento como "Purchase offline" para optimización

### Objetivo Mensajes (WhatsApp Business)

El objetivo "Conversaciones" ya se optimiza hacia personas que abren WhatsApp, no necesita pixel en sitio web. Pero sigue siendo útil tener pixel para retargeting de web visitors.

## 5. Calidad de coincidencia de eventos

### Qué es

Meta puntúa la calidad del matching entre los datos que le envías y sus usuarios. Score del 1 al 10.

### Objetivo mínimo

- Aceptable: 6.5
- Bueno: 7.5+
- Excelente: 8.5+

### Cómo mejorarlo

Enviar más parámetros con cada evento:

- Email hasheado (em)
- Teléfono hasheado (ph)
- Nombre hasheado (fn, ln)
- Ciudad, estado, código postal hasheados
- Fecha de nacimiento hasheada
- Identificador externo (external_id)
- IP del cliente
- User agent del navegador

Más parámetros = mejor matching = mejor optimización.

## 6. Eventos sin actividad reciente

### Diagnóstico

En Events Manager, si un evento muestra "Sin actividad reciente" durante más de 7 días:

- El evento no se está disparando desde el sitio
- Revisar que el código de activación siga presente
- Revisar que el plugin/integración no se haya roto tras un update

### Caso común: después de actualizar WooCommerce

Los plugins de Meta suelen romperse con updates de WooCommerce. Revisar siempre:

- Que el plugin esté activo
- Que el token de API de Conversiones siga siendo válido (expira)
- Que el pixel ID siga siendo el correcto

## 7. Configuración para iOS 14+

### Contexto

Desde iOS 14 con App Tracking Transparency, el tracking web de usuarios de iPhone está limitado. Meta introdujo "Aggregated Event Measurement" para compensar.

### Acción requerida

En Events Manager → Configuración de medición agregada de eventos:

- Verificar que el dominio esté **verificado** (registro DNS TXT o meta tag)
- Priorizar los 8 eventos más importantes del negocio
- El evento de optimización de cada campaña debe estar dentro de los 8 priorizados

### Si no está configurado

Meta limita el tracking y la campaña sub-optimiza. Síntoma típico: costo/conv sube sin razón clara después de iOS release.

## 8. Debugging rápido

### El pixel está instalado pero no veo eventos

1. Probar con Facebook Pixel Helper en incógnito (sin extensiones)
2. Verificar que el dominio no esté en la lista de bloqueo del navegador
3. Revisar la consola del navegador en busca de errores de JavaScript

### Los eventos se duplican

Falta deduplicación por event_id. Revisar integración del plugin/SDK.

### El evento Purchase se dispara pero sin valor

El parámetro `value` no se está enviando. Revisar configuración del plugin o del snippet custom.

### La calidad de coincidencia bajó de golpe

1. Meta hizo un cambio en cómo evalúa algún parámetro
2. Revisar si el sitio dejó de enviar algún campo (ej: email, teléfono)
3. A veces se soluciona solo en 48 horas, otras requiere re-configurar el plugin
