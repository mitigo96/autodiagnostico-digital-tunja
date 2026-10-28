# Autodiagnóstico Digital — Pequeños Negocios de Servicios de Tunja

Prototipo web de autodiagnóstico de transformación digital, desarrollado como
parte del Proyecto de Grado (código 202016907), Ingeniería de Sistemas,
Universidad Nacional Abierta y a Distancia (UNAD), CEAD Tunja.

**Estudiantes:** Miguel Santiago Munévar Blanco, Katherin Julieth Sánchez Cely
**Fase:** 4 — Componente práctico (práctica simulada)
**Nivel de madurez tecnológica (TRL):** TRL 5 — prototipo validado en entorno simulado

## Qué hace

El usuario (propietario o administrador de un pequeño negocio de servicios)
responde un cuestionario de 15 preguntas organizado en cinco dimensiones:

1. Presencia y comunicación digital
2. Gestión de clientes y procesos
3. Uso de datos y colaboración
4. Seguridad, privacidad y respaldo
5. Capacidades de planificación e innovación

Al finalizar, el sistema calcula un **nivel orientativo** por dimensión
(inicial, básico o avanzado) y entrega **recomendaciones graduales y de bajo
costo** asociadas a cada nivel obtenido.

## Tecnología

HTML5, CSS3 y JavaScript puro (sin frameworks ni dependencias externas),
según lo definido en el marco tecnológico del documento maestro. Es una
aplicación 100 % cliente: no requiere servidor, base de datos ni conexión a
Internet para funcionar una vez descargada.

## Cómo ejecutarlo

No requiere instalación. Basta con abrir `index.html` en cualquier navegador
web moderno (Chrome, Edge, Firefox), en computador o en celular.

```
git clone <url-de-este-repositorio>
cd <carpeta-del-repositorio>
# abrir index.html con el navegador
```

También puede publicarse gratuitamente con **GitHub Pages** (Settings →
Pages → branch `main` → carpeta raíz) para compartir un enlace en vivo.

## Arquitectura

El código se organiza en tres módulos independientes dentro de `index.html`,
tal como se documentó en el numeral 8.4 (Marco tecnológico) y 9.7 (Diseño
preliminar del prototipo) del documento maestro:

- **`DATA`** — dimensiones, banco de 15 preguntas con sus opciones y
  puntajes, y catálogo de recomendaciones por dimensión y nivel.
- **`MOTOR`** — motor de clasificación: calcula el puntaje y el nivel de
  cada dimensión a partir de las respuestas (reglas documentadas y
  reproducibles: puntaje 0-2 → inicial, 3-4 → básico, 5-6 → avanzado).
- **`INTERFAZ`** — manejo del estado de la sesión y renderizado de las
  cinco pantallas (bienvenida, cuestionario, procesamiento, resultados,
  recomendaciones).

No hay backend ni almacenamiento persistente: las respuestas viven en
memoria del navegador durante la sesión y se descartan al cerrarla o
recargar la página (requisito no funcional RNF5 del documento maestro).

## Pruebas realizadas

- Verificación sintáctica del código JavaScript.
- Recorrido funcional completo del flujo (bienvenida → contexto →
  cuestionario → procesamiento → resultados → recomendaciones).
- Verificación del motor de clasificación con respuestas de prueba en los
  tres niveles (inicial, básico, avanzado).
- Verificación visual en modo claro y modo oscuro, y en viewport móvil.

## Estado

Prototipo funcional de alcance académico. No incluye pagos, comercio
electrónico, inteligencia artificial avanzada, integración con sistemas
externos, aplicación móvil nativa ni almacenamiento permanente de datos,
conforme a la delimitación tecnológica establecida en el documento maestro.
