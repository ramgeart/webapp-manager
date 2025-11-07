# Manual de Uso - Web App Manager

## Introducción

Web App Manager permite ejecutar sitios web como si fueran aplicaciones independientes en tu sistema. Esta guía te mostrará cómo crear y configurar aplicaciones web.

## Índice

1. [Vista Principal](#vista-principal)
2. [Crear una Nueva Aplicación Web](#crear-una-nueva-aplicación-web)
3. [Configuración Básica](#configuración-básica)
4. [Opciones Avanzadas](#opciones-avanzadas)
5. [Nuevas Funcionalidades](#nuevas-funcionalidades)
6. [Editar Aplicaciones Existentes](#editar-aplicaciones-existentes)

---

## Vista Principal

Al abrir Web App Manager, verás la ventana principal con la lista de aplicaciones web creadas.

**[Captura de pantalla: Ventana principal mostrando la lista de Web Apps]**

Desde aquí puedes:
- **Agregar** nuevas aplicaciones web (botón +)
- **Editar** aplicaciones existentes (botón de lápiz)
- **Eliminar** aplicaciones (botón de papelera)
- **Ejecutar** aplicaciones (doble clic o botón de reproducción)

---

## Crear una Nueva Aplicación Web

### Paso 1: Iniciar la Creación

Haz clic en el botón **"+"** en la barra inferior para abrir el formulario de creación.

**[Captura de pantalla: Botón de agregar resaltado]**

### Paso 2: Información Básica

Se abrirá el formulario "Add a New Web App" donde deberás completar:

**[Captura de pantalla: Formulario completo de "Add a New Web App"]**

---

## Configuración Básica

### Nombre de la Aplicación
- **Campo:** Name
- **Descripción:** El nombre que aparecerá en tu menú de aplicaciones
- **Ejemplo:** "Gmail", "YouTube Music", "WhatsApp Web"

**[Captura de pantalla: Campo Name rellenado]**

### Descripción (Opcional)
- **Campo:** Description
- **Descripción:** Una descripción breve de la aplicación
- **Ejemplo:** "Cliente de correo electrónico de Google"

### Dirección Web
- **Campo:** Address
- **Descripción:** La URL completa del sitio web
- **Ejemplo:** `https://mail.google.com`

**[Captura de pantalla: Campo Address con URL de ejemplo]**

### Icono
Tienes dos opciones para seleccionar el icono:

1. **Buscar en línea:** Haz clic en "Find icons online" para descargar automáticamente los iconos del sitio web
2. **Seleccionar manualmente:** Haz clic en el icono actual para elegir una imagen de tu sistema

**[Captura de pantalla: Selector de iconos mostrando opciones descargadas]**

### Categoría
Selecciona la categoría donde aparecerá la aplicación en tu menú:
- Web (por defecto)
- Internet
- Accesorios
- Juegos
- Gráficos
- Oficina
- Sonido y Video
- Programación
- Educación

**[Captura de pantalla: Desplegable de categorías]**

### Navegador
Selecciona el navegador base para la aplicación (solo aparece si tienes múltiples navegadores instalados):
- Firefox
- Chrome
- Chromium
- Brave
- Edge
- Vivaldi
- Y otros navegadores soportados

**[Captura de pantalla: Selector de navegador]**

---

## Opciones Avanzadas

### Parámetros Personalizados
- **Campo:** Custom parameters
- **Descripción:** Argumentos adicionales de línea de comandos para el navegador
- **Ejemplo:** `--force-dark-mode`

**[Captura de pantalla: Campo de parámetros personalizados]**

### Perfil Aislado (Chromium/Chrome)
- **Opción:** Isolated profile
- **Descripción:** Cuando está activado, la aplicación usa su propio perfil de navegador separado
- **Beneficio:** Mantiene cookies, historial y configuración separados de tu navegador principal

**[Captura de pantalla: Switch de Isolated profile activado]**

### Barra de Navegación (Firefox)
- **Opción:** Navigation bar
- **Descripción:** Muestra u oculta la barra de navegación en aplicaciones basadas en Firefox
- **Nota:** Solo visible para navegadores Firefox

**[Captura de pantalla: Switch de Navigation bar en Firefox]**

---

## Nuevas Funcionalidades

### 1. GPU Enabled (Nuevo)

**Disponible para:** Navegadores basados en Chromium (Chrome, Brave, Edge, Vivaldi, etc.)

**¿Qué hace?**
Permite deshabilitar la aceleración por GPU en la aplicación web. Útil cuando experimentas:
- Problemas gráficos o visuales
- Pantallazos negros
- Renderizado incorrecto
- Consumo excesivo de memoria de video

**Cómo usar:**
1. Localiza el switch "GPU Enabled" debajo de "Navigation Bar"
2. Por defecto está **ACTIVADO** (GPU habilitado)
3. Desactívalo si experimentas problemas gráficos

**[Captura de pantalla: Switch GPU Enabled activado y desactivado]**

**Efecto técnico:**
- Cuando está **desactivado**, agrega el flag `--disable-gpu` al comando de ejecución
- Ejemplo: `google-chrome-stable --app="https://example.com" --disable-gpu`

**Cuándo desactivarlo:**
- ✓ Pantallas negras o vacías en la aplicación
- ✓ Problemas de renderizado
- ✓ Crashes relacionados con la GPU
- ✓ Uso en máquinas virtuales sin aceleración 3D

### 2. Profile Location (Nuevo)

**Disponible para:** Navegadores basados en Chromium con "Isolated profile" activado

**¿Qué hace?**
Permite seleccionar una ubicación personalizada donde se creará el perfil aislado de la aplicación, en lugar de usar la ubicación por defecto (`~/.local/share/ice/profiles`).

**Cómo usar:**
1. Asegúrate de que "Isolated profile" esté **ACTIVADO**
2. Aparecerá automáticamente el selector "Profile location"
3. Haz clic en el selector de carpetas
4. Navega y selecciona la carpeta donde quieres almacenar los perfiles

**[Captura de pantalla: Selector de Profile location visible cuando Isolated profile está ON]**

**¿Dónde se crea el perfil?**
Si seleccionas `/home/usuario/mis-perfiles`, el perfil se creará en:
```
/home/usuario/mis-perfiles/NombreApp1234/
```

**Casos de uso:**
- ✓ Organizar perfiles en una carpeta específica
- ✓ Almacenar perfiles en una partición diferente
- ✓ Facilitar copias de seguridad
- ✓ Compartir perfiles entre sistemas (en unidad externa)

**Validación automática:**
- Si la carpeta no existe, se **creará automáticamente**
- Si no tiene permisos de escritura, usará la ubicación por defecto
- Se muestra un mensaje de advertencia si hay problemas

**[Captura de pantalla: Diálogo de selección de carpeta]**

### 3. Ventana Privada/Incógnito

- **Opción:** Private/Incognito Window
- **Descripción:** Lanza la aplicación en modo privado/incógnito
- **Disponible para:** Todos los navegadores

**[Captura de pantalla: Switch Private Window]**

---

## Editar Aplicaciones Existentes

### Paso 1: Seleccionar la Aplicación
En la ventana principal, selecciona la aplicación que deseas editar de la lista.

### Paso 2: Abrir el Editor
Haz clic en el botón de **editar** (ícono de lápiz) o presiona `Ctrl+E`.

**[Captura de pantalla: Botón de editar resaltado]**

### Paso 3: Modificar Configuración
Se abrirá el formulario "Edit Web App" con todos los campos prellenados. Las opciones son las mismas que al crear una nueva aplicación.

**[Captura de pantalla: Formulario de "Edit Web App" con datos cargados]**

**Diferencias con "Add a New Web App":**
- No se puede cambiar el navegador base (el campo está oculto)
- Todos los demás campos son editables

### Paso 4: Guardar Cambios
Haz clic en **OK** para guardar los cambios.

---

## Ejemplo Completo: Crear Gmail como Aplicación

### Configuración Recomendada

```
Name: Gmail
Description: Cliente de correo de Google
Address: https://mail.google.com
Icon: (usar "Find icons online")
Category: Internet
Browser: Chrome/Chromium

Opciones:
✓ Isolated profile: ON
✓ GPU Enabled: ON
✓ Profile location: (dejar por defecto o seleccionar carpeta personalizada)
✗ Private Window: OFF
```

**[Captura de pantalla: Formulario completo de Gmail configurado]**

### Resultado

Una vez creada, la aplicación aparecerá:
- En la lista de Web App Manager
- En tu menú de aplicaciones (categoría Internet)
- Con su propio icono de Gmail

**[Captura de pantalla: Gmail en la lista de aplicaciones]**

**[Captura de pantalla: Gmail en el menú del sistema]**

---

## Solución de Problemas

### La aplicación muestra pantalla negra
**Solución:** Desactiva "GPU Enabled"

### La aplicación usa mi sesión del navegador principal
**Solución:** Activa "Isolated profile"

### No puedo encontrar el icono de la aplicación
**Solución:** Usa "Find icons online" o selecciona manualmente un archivo PNG/SVG

### Error al crear el perfil personalizado
**Solución:** Verifica que la carpeta tenga permisos de escritura o usa la ubicación por defecto

### Las opciones GPU/Profile location no aparecen
**Solución:** Estas opciones solo están disponibles para navegadores Chromium. Selecciona Chrome, Brave, Edge o Vivaldi.

---

## Atajos de Teclado

| Atajo | Acción |
|-------|--------|
| `Ctrl+N` | Nueva aplicación web |
| `Ctrl+E` | Editar aplicación seleccionada |
| `Ctrl+D` | Eliminar aplicación seleccionada |
| `Ctrl+K` | Mostrar atajos de teclado |
| `Ctrl+Q` o `Ctrl+W` | Salir |
| `Escape` | Cancelar/Volver |

---

## Navegadores Soportados

### Basados en Chromium (con GPU Enabled y Profile Location)
- Google Chrome
- Chromium
- Brave Browser
- Microsoft Edge
- Vivaldi
- Ungoogled Chromium
- Yandex Browser
- Thorium

### Basados en Firefox (con Navigation Bar)
- Firefox
- Firefox Developer Edition
- Firefox ESR
- LibreWolf
- Waterfox
- Floorp
- Zen Browser

### Otros
- GNOME Web (Epiphany)
- Falkon

---

## Notas Importantes

1. **Perfiles aislados** son recomendados para mantener separadas las sesiones de cada aplicación web
2. **GPU Enabled** debe desactivarse solo si experimentas problemas gráficos
3. **Profile location** personalizada es útil para organización, pero la ubicación por defecto funciona perfectamente
4. Los **iconos descargados** se almacenan en `~/.local/share/ice/icons/`
5. Los **archivos desktop** se crean en `~/.local/share/applications/`

---

## Soporte y Recursos

- **Repositorio GitHub:** https://github.com/linuxmint/webapp-manager
- **Reportar problemas:** https://github.com/linuxmint/webapp-manager/issues
- **Documentación oficial:** README.md en el repositorio

---

**Versión del manual:** 1.0  
**Última actualización:** Noviembre 2025  
**Funcionalidades documentadas:** GPU Enabled, Profile Location, todas las opciones base
