# DOC-QP-017 — Preparación de herramientas de desarrollo

| Campo | Información |
|---|---|
| Código | DOC-QP-017 |
| Apartado | 5.1 — Herramientas |
| Versión | 0.1 |
| Fecha | 19/11/2026 |
| Estado | En revisión — verificación local pendiente |
| Responsable | Responsable del proyecto |
| Sistema operativo | Windows |

## 1. Objetivo

Dejar operativo el equipo de desarrollo de QualityPrint-SGC mediante la comprobación de las herramientas definidas en [DOC-QP-002](../01_proyecto/DOC-QP-002_organizacion_inicial_del_proyecto.md). Esta guía no instala software por sí sola ni acredita que esté instalado.

## 2. Herramientas y criterios de aceptación

| Actividad | Herramienta | Función exacta | Evidencia requerida |
|---|---|---|---|
| 5.1.1 | Visual Studio Code | Editar código Python, HTML, CSS y documentación; abrir la terminal integrada. | VS Code abre y `code --version` devuelve una versión, o se comprueba la versión en Ayuda > Acerca de. |
| 5.1.2 | Python | Ejecutar el backend Flask y gestionar dependencias con pip. | Python y pip muestran versión; se selecciona la versión a utilizar. |
| 5.1.3 | Git | Registrar y sincronizar cambios de código. | `git --version` devuelve versión. |
| 5.1.4 | GitHub | Alojar el repositorio y su historial remoto. | Repositorio existente y rama main comprobados; conexión local pendiente en 5.2.8. |
| 5.1.5 | Chrome y Firefox | Probar navegación y compatibilidad del frontend. | Ambos navegadores abren y se identifica su versión. |

## 3. Procedimiento en Windows

### 3.1. Comprobar lo instalado antes de descargar

Abrir Windows PowerShell desde Inicio. Ejecutar cada línea por separado:

```powershell
code --version
py --version
git --version
py -m pip --version
```

Si `py` no está disponible, ejecutar `python --version` y `python -m pip --version`. Registrar los resultados reales sin incluir datos personales. Una ausencia en PATH no implica necesariamente que el programa no esté instalado: comprobar el menú Inicio y abrir una terminal nueva tras instalarlo.

### 3.2. Visual Studio Code

Si falta, descargar desde [Microsoft — VS Code para Windows](https://code.visualstudio.com/docs/setup/windows), elegir el instalador correspondiente a la arquitectura del equipo y habilitar la incorporación a PATH cuando se ofrezca. Abrir VS Code. Instalar la extensión oficial **Python** de Microsoft (identificador `ms-python.python`). Comprobar versión y terminal integrada.

### 3.3. Python

Base propuesta: Python 3.13.x de 64 bits. Si ya existe Python 3.12 o 3.14, registrar su versión antes de decidir si hace falta otra instalación. No eliminar versiones existentes.

Si falta, usar el instalador oficial disponible en [Python para Windows](https://docs.python.org/3/using/windows.html). Si se usa Python Install Manager, instalar la versión objetivo con `py install 3.13`; comprobar con `py -3.13 --version` y `py -3.13 -m pip --version`. Para una instalación clásica, habilitar PATH si el instalador ofrece esa opción y verificar Python y pip en una terminal nueva.

### 3.4. Git

Si falta, descargar el instalador para la arquitectura del equipo desde [Git para Windows](https://git-scm.com/install/windows). Elegir la opción que permite usar Git en la terminal de Windows. Comprobar `git --version`.

Consultar, sin modificar, la identidad configurada:

```powershell
git config --global user.name
git config --global user.email
```

Si falta, se definirá la identidad antes del primer commit local. Puede utilizarse el correo noreply asociado a la cuenta; no publicar credenciales. Véase [configuración de identidad Git](https://docs.github.com/en/get-started/git-basics/setting-your-username-in-git). No es necesario compartir el correo por chat.

### 3.5. GitHub

Reutilizar [el repositorio existente](https://github.com/MartinValenzu/SISTEMA-DE-GESTION-DE-CALIDAD-QualityPrint-FICTICIA-), rama `main`. No crear un repositorio duplicado. La conexión desde el equipo local, autenticación y primer intercambio de cambios quedan para 5.2.8.

### 3.6. Navegadores de prueba

Abrir Chrome y Firefox. Consultar sus versiones en Ayuda > Acerca de Google Chrome y Ayuda > Acerca de Firefox. Si falta uno, instalarlo desde su distribuidor oficial. La validación funcional y de compatibilidad de la aplicación se hará en la etapa 7.

## 4. Registro de comprobación

| Herramienta | Resultado registrado | Estado |
|---|---|---|
| Visual Studio Code | Pendiente de evidencia local | Pendiente |
| Python y pip | Pendiente de evidencia local | Pendiente |
| Git | Pendiente de evidencia local | Pendiente |
| GitHub remoto | Repositorio activo; rama main existente | Confirmado |
| Chrome y Firefox | Pendiente de evidencia local | Pendiente |

## 5. Checklist de cierre

- [ ] 5.1.1. Instalar o comprobar Visual Studio Code.
- [ ] 5.1.2. Instalar o comprobar Python y pip.
- [ ] 5.1.3. Instalar o comprobar Git.
- [x] 5.1.4. Configurar cuenta y repositorio remoto de GitHub (reutilizado de etapa 1).
- [ ] 5.1.5. Preparar los navegadores de pruebas.

No marcar una actividad local como completada hasta recibir evidencia. No instalar todavía Flask ni SQLAlchemy ni crear una base de datos; esas actividades corresponden a 5.2.

## 6. Control de cambios

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Guía y criterios verificables de preparación del equipo | En revisión |

**Siguiente apartado:** 5.2 — Configuración técnica, después de verificar las herramientas.
