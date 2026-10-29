# Equipo Frontend 33 · TP2

Aplicación React que continúa el perfil grupal realizado en el TP1. Reúne los perfiles de Jonatan, Gonzalo y Gabriel, una biblioteca de recursos de frontend, una consulta pública a Open Library, el árbol de componentes y una bitácora. La interfaz comparte un menú lateral en todas las pantallas y se adapta a celulares.

## Índice

- [Integrantes](#integrantes)
- [Ejecutar el proyecto](#ejecutar-el-proyecto)
- [Recorrido y funcionalidades](#recorrido-y-funcionalidades)
- [Estructura y decisiones](#estructura-y-decisiones)
- [Publicación y entrega](#publicación-y-entrega)
- [Uso de inteligencia artificial](#uso-de-inteligencia-artificial)
- [Revisión pendiente](#revisión-pendiente)

## Integrantes

- [Jonatan Emanuel Uribio](https://github.com/JonatanUribio7749)
- [Gonzalo Moretti](https://github.com/moregonza1975-rgb)
- [Gabriel Zarza](https://github.com/gabrielzarza741)

Los datos personales y cuentas provienen del material del TP1 y deben ser confirmados por cada integrante. La edad es la que figuraba allí y puede haber cambiado. El avatar de Gabriel es tipográfico porque el TP1 no contenía una foto confirmada.

## Ejecutar el proyecto

Requisitos: Node.js 18 o superior y npm. Desde la carpeta del proyecto:

```bash
npm install
npm run dev
```

Abrir la dirección que indica Vite, normalmente `http://localhost:5173`. Para generar y probar la versión de producción:

```bash
npm run build
npm run preview
```

La API y las fuentes web requieren conexión. Las fuentes del sistema se usan como alternativa. No se necesitan claves privadas ni variables de entorno.

## Recorrido y funcionalidades

- **Inicio:** presentación del equipo, detalle interactivo sobre su identidad y tarjetas enlazadas a los perfiles.
- **Perfiles:** pantalla React por integrante, con información, gustos, GitHub y un botón que muestra frases o datos relacionados con la persona.
- **Recursos:** 24 registros en `src/data/recursos.json`, renderizados mediante `ResourceCard`. La búsqueda y el filtro de categoría se combinan; se informa si no hay resultados y se puede restablecer la lista. Cada tarjeta despliega información adicional y un enlace de consulta.
- **API pública:** Open Library proporciona hasta doce libros relacionados con programación, con título, autor y año cuando están disponibles. La pantalla informa la carga y los errores, y permite reintentar. Consulta: `https://openlibrary.org/search.json?subject=computer_programming&limit=12&fields=key,title,author_name,first_publish_year`. Se cancela la solicitud al salir de la pantalla. La selección es automática y los títulos no representan recomendaciones individuales del equipo.
- **Árbol:** representación de los componentes que se renderizan, incluidos los que reciben datos por props.
- **Bitácora:** síntesis de la evolución desde TP1 y de las decisiones de esta versión.

Las rutas se manejan con React Router. La sidebar indica la sección activa; en móvil se abre y cierra con un botón. Hay una pantalla para rutas inexistentes y enlaces internos para continuar o volver sin depender del navegador.

## Estructura y decisiones

```text
src/
  main.jsx               Componentes, rutas, estado y consulta a la API
  styles.css             Identidad visual y estilos adaptables
  data/recursos.json     Catálogo local
public/img/              Fotografías provenientes del TP1
index.html               Punto de entrada
vercel.json              Reescritura de rutas para recargar enlaces directos
```

El proyecto usa React 18, React Router 6, Vite y CSS. `Layout` mantiene la navegación y define las rutas; `TarjetaIntegrante`, `Avatar`, `Encabezado` y `ResourceCard` reutilizan componentes con distintos datos. `useState` controla menú, filtros e interacciones; `useEffect` administra la consulta externa. Los datos personales están en `integrantes`, en `src/main.jsx`; el catálogo se edita en el JSON.

La paleta verde toma como referencia la identidad del TP1 y se amplía con superficies claras y acentos cálidos. Se utilizan HTML semántico, etiquetas para campos, foco visible, mensajes de estado y soporte para preferencia de movimiento reducido.

## Publicación y entrega

**Repositorio público:** pendiente de crear por el equipo.  
**Sitio publicado en Vercel:** pendiente de publicar por el equipo.

1. Crear un repositorio público independiente para TP2 y subir el contenido de esta carpeta, incluido `package-lock.json` si se generó. No subir `node_modules` ni `dist`.
2. Invitar a los integrantes registrados al repositorio y comprobar que aceptaron las invitaciones. Completar la responsabilidad real de cada persona en este README.
3. Importar el repositorio en Vercel. Usar Vite, `npm run build` y directorio de salida `dist`. El archivo `vercel.json` permite abrir y recargar las rutas directamente.
4. Reemplazar los dos textos «pendiente» de arriba por los enlaces reales. Agregar capturas y un índice con enlaces internos para aspirar al nivel superior de documentación.
5. Abrir el repositorio y el sitio sin iniciar sesión; recorrer todas las pantallas, recargar sus URL, probar menú móvil, perfiles, búsqueda, filtro, ausencia de resultados y API. Finalmente cargar el enlace del repositorio en la planilla de la cátedra.

## Uso de inteligencia artificial

- **Aplicación:** OpenAI Codex. **Modelo:** GPT-6 (información indicada por el entorno de trabajo).
- **Uso en esta versión:** asistencia a pedido de Jonatan para interpretar la consigna, preparar código React, estilos y documentación a partir de los archivos facilitados. La información del TP1 y los textos se adaptaron al nuevo proyecto.
- **Trabajo de otros integrantes:** pendiente de informar por cada persona; no se atribuyen usos de herramientas o tareas no confirmados. El equipo debe revisar el código y el contenido, registrar sus modificaciones reales y completar esta declaración antes de entregar.
- **Imágenes:** se reutilizaron fotografías presentes en el TP1; el avatar de Gabriel se compone con iniciales. En esta versión no se generaron imágenes con IA.

## Revisión pendiente

Confirmar nombres, cuentas, edad, ciudad y contenido de cada perfil; especialmente los datos y la presentación de Gabriel, que eran provisionales en el TP1. Confirmar la nómina de integrantes registrados y agregar cualquier integrante que falte. Completar colaboraciones, capturas, enlaces reales, invitaciones y publicación; no se pueden demostrar hasta que el equipo los gestione. Revisar los derechos y la autorización para publicar las fotos.
