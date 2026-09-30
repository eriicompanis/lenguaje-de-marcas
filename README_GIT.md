# Guía Básica de Git (Flujo de Una Sola Rama)

Esta guía contiene los comandos esenciales y el flujo de trabajo paso a paso para proyectos donde se trabaja exclusivamente en la rama principal (`main` o `master`).

## 1. Comandos Esenciales

| Categoría | Comando | Descripción |
| :--- | :--- | :--- |
| **Configuración** | `git config --global user.name "Nombre"` | Configura el nombre para tus *commits*. |
| **Configuración** | `git config --global user.email "correo"` | Configura tu correo electrónico. |
| **Configuración** | `git clone [url]` | Descarga un repositorio completo a tu computadora. |
| **Configuración** | `git init` | Convierte la carpeta actual en un repositorio local. |
| **Trabajo Diario** | `git status` | Muestra el estado actual de tus archivos (modificados, listos). |
| **Trabajo Diario** | `git add .` | Prepara **todos** los archivos modificados para ser guardados. |
| **Trabajo Diario** | `git commit -m "Mensaje"` | Guarda los cambios preparados en tu historial local. |
| **Sincronización**| `git pull` | Descarga cambios del servidor y los junta con los tuyos. |
| **Sincronización**| `git push` | Envía tus *commits* locales al servidor. |
| **Historial** | `git log --oneline` | Muestra un historial resumido de los *commits*. |
| **Deshacer** | `git restore [archivo]` | Deshace los cambios no guardados en un archivo. |

---

## 2. Flujo de Trabajo Diario (Single Branch Workflow)

Este es el ciclo que repetirás constantemente al escribir código trabajando solo en la rama principal.

### Paso 1: Obtener la última versión
Antes de empezar a programar en tu día, asegúrate de tener los últimos cambios si trabajas con más personas o desde otro equipo.
```bash
git pull
```

### Paso 2: Trabajar en tus archivos
Escribe tu código, modifica, crea o elimina archivos normalmente en tu editor.

### Paso 3: Revisar el estado
Comprueba qué archivos han sido modificados para asegurarte de que vas a subir lo correcto.
```bash
git status
```

### Paso 4: Preparar los cambios
Añade todos los archivos modificados al área de preparación (*Staging Area*).
```bash
git add .
```

### Paso 5: Guardar el trabajo (Commit)
Crea un punto de guardado en tu historial local con un mensaje claro de lo que hiciste.
```bash
git commit -m "Añadida la página de inicio y corregido el menú"
```

### Paso 6: Sincronizar (Subir a la nube)
Envía tus cambios al repositorio remoto (ej. GitHub, GitLab). 
*Nota: Si alguien más subió código mientras tú trabajabas, Git te pedirá que hagas `git pull` antes de dejarte hacer `git push`.*
```bash
git push
```

---

## 3. Extras Útiles

### Ignorar archivos (`.gitignore`)
Crea un archivo llamado `.gitignore` en la raíz de tu proyecto y escribe dentro los nombres de los archivos o carpetas que no quieres que Git rastree (por ejemplo, contraseñas, carpetas como `node_modules/` o archivos temporales).
