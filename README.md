# Plantilla · Práctica 2 · Tema 2 · Entornos de Desarrollo (DAW)

Este repositorio es el punto de partida de la práctica **«Tu entorno de desarrollo como código»**.
Sigue el enunciado paso a paso: **no tienes que programar nada**.

## Qué hay aquí

| Carpeta / archivo | Qué es | ¿Lo tocas? |
|---|---|---|
| `.devcontainer/devcontainer.json` | La «receta» de tu entorno de desarrollo | Sí, siguiendo el enunciado |
| `src/java/Factura.java` | Programa de ejemplo en Java (lo da el profesor) | No |
| `src/ts/factura.ts` | El mismo programa en TypeScript (lo da el profesor) | No |
| `package.json` | Manifiesto de dependencias del proyecto | Solo en el paso 17 |
| `tsconfig.json` | Configuración del compilador de TypeScript | No |
| `fragmentos/` | Los textos que tendrás que copiar y pegar en cada paso | Solo para copiar |
| `docs/entorno.md` | Tu documentación de la práctica | Sí, la rellenas tú |
| `docs/capturas/` | Aquí subes las pocas capturas que se piden | Sí |

## Cómo arrancar este proyecto

1. Pulsa **Code → Codespaces → Create codespace on main**.
2. Espera a que termine de construirse el entorno.
3. Pulsa `Ctrl+Shift+B` (Windows) o `Cmd+Shift+B` (Mac) para compilar y ejecutar todo.

## Abrir JupyterLab

JupyterLab se instala en el entorno, pero hay que iniciar el servidor cuando se vaya a usar.
En el terminal del Codespace ejecuta:

```bash
jupyter lab --ip=0.0.0.0 --no-browser
```

El Codespace reenviará el puerto 8888; abre ese puerto desde la pestaña **Ports** y usa la
URL con token que muestra Jupyter en el terminal. No compartas esa URL: el token permite
acceder al servidor.
