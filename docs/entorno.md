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
```bash
bash: java: command not found
```

**Resultado de node -v**
```bash
bash: node: command not found
```

¿Por qué crees que aparece ese mensaje? (relaciónalo con la diapositiva «Problemas habituales del entorno»)

**Respuesta:**
> Porque al no tener instalado java ni node en el codespace, no se han añadido al PATH

### 1.2. Después de la 1.ª reconstrucción (paso 5)

Resultado de `java -version`, `node -v` y `jupyter lab --version` **después**:

```bash
openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
v24.22.1
4.6.4
```

¿Qué líneas nuevas han aparecido en `devcontainer.json`? Explica con tus palabras qué hace cada una:

```json
"ghcr.io/devcontainers/features/python:1": {
  "installJupyterlab": true
}
```

**Respuesta:**
> La primera muestra la fuente de la dependencia Python
> La segunda indica instalar el editor Jupyter Lab
> La tercera cierra ese apartado

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
| Code Spell Checker      | Busca errores de ortografía. | Marca palabras que pueden estar mal escritas y sugiere correcciones. | No, porque me ensucia el entorno con falsos positivos al no detectar el español. |

¿Qué diferencia hay entre instalar una extensión **solo desde el panel** y añadirla **también a `devcontainer.json`**?

**Respuesta:**
> Si la instalo desde el panel, solo queda instalada en mi entorno. Si la añado a `devcontainer.json`, se instala cada vez que se crea el entorno, para que todos tengan la misma extensión.

---

## 3. Personalización y automatización (CE 2.c)

- **Tema visual elegido** (paso 10) y por qué:

  **Respuesta:**
  > Catppuccin Mocha + Material Icons, porque estoy acostumbrado a eso.
- **Ajuste del proyecto** (paso 10). ¿Qué archivo se ha creado y qué contiene?

  ```json
  {
     "editor.formatOnSave": true
  }
  ```

- **Atajo de teclado** (paso 11). ¿Qué acción, qué combinación y para qué te sirve?
  **Respuesta:**
  > Cmd + Shift + ; --> Sirve para hacer Rebuild del Codespace.
- **Snippet** (paso 12). ¿Qué escribes y qué aparece?
  **Respuesta:**
  > Escribo cabecera y se genera el comentario en bloque establecido en el snippet.
- **Automatización al crear el entorno** (paso 14). ¿Qué hace `postCreateCommand` y qué archivos/carpetas han aparecido después de reconstruir?
  **Respuesta:**
  > `postCreateCommand` ejecuta `npm install` al crear el entorno para instalar las dependencias definidas por el proyecto. Después aparece o se actualiza la carpeta `node_modules/`; las dependencias y sus versiones se describen en `package.json` y `package-lock.json`. Las carpetas `build/` y `dist/` se generan al ejecutar las tareas de compilación, no por `postCreateCommand`.
- **Tareas** (paso 13). ¿Cuántas tareas hay en `tasks.json` y qué hace cada una?
  **Respuesta:**
  > Hay tres tareas en `.vscode/tasks.json`: la de Java compila `Factura.java`, crea `build/factura.jar` y lo ejecuta; la de TypeScript compila con `npm run build` y ejecuta el resultado con `npm start`; y **Build completo** ejecuta ambas tareas en secuencia.

¿Qué parte de toda esta configuración es **personal** (solo para ti) y qué parte es **del proyecto** (la recibe cualquiera que abra el repositorio)?

**Respuesta:**
> Es personal lo que configuro en mi perfil de VS Code y no guardo en el repositorio, como el tema activo o mis atajos de teclado. Es del proyecto lo que está guardado en sus archivos: `.devcontainer/devcontainer.json` define el entorno, las extensiones y `postCreateCommand`; `.vscode/settings.json` comparte los ajustes del editor; `.vscode/tasks.json` define las tareas; y `.vscode/daw.code-snippets` contiene el snippet. Así, cualquiera que abra el repositorio puede recibir esa configuración compartida.
---

## 4. Ejecutables de diferentes lenguajes en el mismo entorno (CE 2.e)

Salida completa de la tarea **Build completo** (paso 15):

```text
=== FACTURA generada con Java 27 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR

=== FACTURA generada con Node.js v24.22.1 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
```

| Lenguaje   | Archivo fuente          | Herramienta que lo traduce | Archivo generado | Cómo se ejecuta |
| ---------- | ----------------------- | -------------------------- | ---------------- | --------------- |
| Java       | `src/java/Factura.java` | `javac`                    | `build/java/Factura.class` y `build/factura.jar` | `java -jar build/factura.jar` |
| TypeScript | `src/ts/factura.ts`     | `tsc` (TypeScript Compiler) | `dist/factura.js` | `node dist/factura.js` |

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

> [!WARNING]
> No funciona Jupyter Lab

---

## 5. Sistema de actualizaciones (CE 2.d)

| Elemento                               | ¿Quién lo actualiza? | Modo (automático / manual / ninguno) | Qué he configurado yo |
| -------------------------------------- | -------------------- | ------------------------------------ | --------------------- |
| El editor de Codespaces                | GitHub / Microsoft   | Automático                           | Uso el editor proporcionado por Codespaces; no fijo su versión. |
| Las extensiones                        | VS Code Marketplace  | Automático                           | Las extensiones del proyecto se indican en `devcontainer.json`; VS Code las instala al crear el entorno y gestiona sus actualizaciones. |
| Java                                   | Feature de Dev Containers | Manual (al reconstruir el entorno) | He fijado la versión principal 21 en `devcontainer.json`; al reconstruir se instala esa versión. |
| Node.js                                | Feature de Dev Containers | Manual (al reconstruir el entorno) | He añadido la feature de Node.js sin fijar una versión concreta. |
| Dependencias npm (lodash, typescript…) | npm                  | Instalación automática; actualización manual | `postCreateCommand` ejecuta `npm install`; las versiones están fijadas en `package.json` y `package-lock.json`. |

Versión de Java **antes** (paso 5) y **después** (paso 18):

**antes**
```bash
openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
```

**despues**
```bash
openjdk version "21" 2023-09-19 LTS
OpenJDK Runtime Environment Microsoft-8425986 (build 21+35-LTS)
OpenJDK 64-Bit Server VM Microsoft-8425986 (build 21+35-LTS, mixed mode, sharing)
```

Resultado de `npm outdated` (paso 17):

```text
Package         Current    Wanted   Latest  Location                    Depended by
@types/lodash  4.14.202  4.14.202  4.17.27  node_modules/@types/lodash  plantilla-entorno-daw-ismael
@types/node    20.11.30  20.11.30   26.6.5  node_modules/@types/node    plantilla-entorno-daw-ismael
lodash          4.17.20   4.17.20   4.18.1  node_modules/lodash         plantilla-entorno-daw-ismael
typescript        5.4.5     5.4.5    7.0.2  node_modules/typescript     plantilla-entorno-daw-ismael
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```text
lodash vulnerable to Prototype Pollution via array path bypass in `_.unset` and `_.omit` - https://github.com/advisories/GHSA-f23m-r3pf-42rh
Lodash has Prototype Pollution Vulnerability in `_.unset` and `_.omit` functions - https://github.com/advisories/GHSA-xxjr-mmjv-4gpg
fix available via `npm audit fix --force`
Will install lodash@4.18.1, which is outside the stated dependency range
node_modules/lodash

1 high severity vulnerability

To address all issues, run:
  npm audit fix --force
```

Resultado de `npm audit` **después**:

```text
found 0 vulnerabilities
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo.

**Respuesta:**
> Dejaría que Codespaces y VS Code gestionen automáticamente las actualizaciones del editor y las extensiones, pero probaría los cambios importantes antes de que el equipo dependa de ellos. Fijaría las versiones principales de Java y Node.js en la configuración del contenedor y mantendría las dependencias npm registradas en `package-lock.json`, para que las cinco personas usen las mismas herramientas y versiones. Revisaría periódicamente las actualizaciones y `npm audit`; aplicaría cuanto antes las actualizaciones de seguridad, como la de lodash que eliminó las vulnerabilidades, y probaría las demás antes de incorporarlas para evitar que una actualización rompa el proyecto.

---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).

> Aviso:
> No he conseguido que funcione Jupyter

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.

**Respuesta:**
> Al describir el entorno como código, todos pueden recrear las mismas herramientas y versiones automáticamente, sin tener que instalar y configurar cada programa a mano. En un equipo con Mac y Windows, el contenedor ofrece un entorno común, lo que reduce diferencias entre sistemas y problemas del tipo «en mi ordenador sí funciona». Además, la configuración queda versionada con el proyecto y se puede revisar o actualizar de forma compartida.
