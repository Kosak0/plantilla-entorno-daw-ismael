# Documentación de mi entorno de desarrollo · Práctica 2

**Ismael Navas Soto:**
**[URL de mi repositorio:](https://github.com/Kosak0/plantilla-entorno-daw-ismael)**

> Rellena cada apartado a medida que avanzas. Donde pone «pega aquí», copia el texto
> de la terminal (no hace falta captura). Escribe con tus palabras: no se valora la longitud,
> sino que se note que entiendes lo que has hecho.

---

## 1. Instalación de entornos (CE 2.a)

### 1.1. Entorno vacío (paso 3)

Resultado de `java -version` y `node -v` **antes** de instalar nada:

**Resultado de java -version**
> bash: java: command not found

**Resultado de node -v**
> bash: node: command not found

¿Por qué crees que aparece ese mensaje? (relaciónalo con la diapositiva «Problemas habituales del entorno»)

> Porque al no tener instalado java ni node en el codespace, no se han añadido al PATH

### 1.2. Después de la 1.ª reconstrucción (paso 5)

Resultado de `java -version`, `node -v` y `jupyter lab --version` **después**:

> openjdk version "27" 2026-09-15
> OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
> OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
> v24.22.1
> 4.6.4

¿Qué líneas nuevas han aparecido en `devcontainer.json`? Explica con tus palabras qué hace cada una:

>

### 1.3. Comparativa de los dos IDE (paso 6)

| Aspecto | Editor de GitHub Codespaces | JupyterLab |
| ------- | --------------------------- | ---------- |
| ¿Libre o propietario? | Propietario (basado en VS Code). | Libre y de código abierto. |
| Licencia / responsable | GitHub / Microsoft. | BSD-3-Clause / Project Jupyter. |
| Coste y límites | Free: 120 h y 15 GB/mes; Pro: 180 h y 20 GB/mes. Excedentes, de pago. | Gratis; el alojamiento puede tener coste. |
| ¿Fuera de GitHub? | No. VS Code sí puede usarse aparte. | Sí, localmente o en otro servidor. |
| Lo que más me ha gustado |No depende de mi dispositivo|Que no carga, por lo que me ahorro trabajo|
| Lo que menos me ha gustado |No tengo mis plugins y configs|No carga|
| ¿Para qué lo elegiría? |Para algun proyecto ligero|Para desesperar a mis enemigos|

---

## 2. Módulos y extensiones (CE 2.b)

| Extensión               | ¿Para qué sirve? | ¿Qué cambió al instalarla? | ¿La mantengo? ¿Por qué? |
| ----------------------- | ---------------- | -------------------------- | ----------------------- |
| Extension Pack for Java | Añade herramientas para programar en Java. | Ayuda a escribir, ejecutar y revisar el código. | Sí, porque necesito trabajar con Java en la práctica. |
| Code Spell Checker      | Busca errores de ortografía. | Marca palabras que pueden estar mal escritas y sugiere correcciones. | Sí, porque ayuda a revisar mis textos y comentarios. |

¿Qué diferencia hay entre instalar una extensión **solo desde el panel** y añadirla **también a `devcontainer.json`**?

>

---

## 3. Personalización y automatización (CE 2.c)

- **Tema visual elegido** (paso 10) y por qué:
- **Ajuste del proyecto** (paso 10). ¿Qué archivo se ha creado y qué contiene?

```
pega aquí el contenido de .vscode/settings.json
```

- **Atajo de teclado** (paso 11). ¿Qué acción, qué combinación y para qué te sirve?
- **Snippet** (paso 12). ¿Qué escribes y qué aparece?
- **Automatización al crear el entorno** (paso 14). ¿Qué hace `postCreateCommand` y qué archivos/carpetas han aparecido después de reconstruir?
- **Tareas** (paso 13). ¿Cuántas tareas hay en `tasks.json` y qué hace cada una?

¿Qué parte de toda esta configuración es **personal** (solo para ti) y qué parte es **del proyecto** (la recibe cualquiera que abra el repositorio)?

>

---

## 4. Ejecutables de diferentes lenguajes en el mismo entorno (CE 2.e)

Salida completa de la tarea **Build completo** (paso 15):

```
pega aquí
```

| Lenguaje   | Archivo fuente          | Herramienta que lo traduce | Archivo generado | Cómo se ejecuta |
| ---------- | ----------------------- | -------------------------- | ---------------- | --------------- |
| Java       | `src/java/Factura.java` |                            |                  |                 |
| TypeScript | `src/ts/factura.ts`     |                            |                  |                 |

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

>

---

## 5. Sistema de actualizaciones (CE 2.d)

| Elemento                               | ¿Quién lo actualiza? | Modo (automático / manual / ninguno) | Qué he configurado yo |
| -------------------------------------- | -------------------- | ------------------------------------ | --------------------- |
| El editor de Codespaces                |                      |                                      |                       |
| Las extensiones                        |                      |                                      |                       |
| Java                                   |                      |                                      |                       |
| Node.js                                |                      |                                      |                       |
| Dependencias npm (lodash, typescript…) |                      |                                      |                       |

Versión de Java **antes** (paso 5) y **después** (paso 18):

```
pega aquí
```

Resultado de `npm outdated` (paso 17):

```
pega aquí
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```
pega aquí
```

Resultado de `npm audit` **después**:

```
pega aquí
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo.

>

---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).

>

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.

>
