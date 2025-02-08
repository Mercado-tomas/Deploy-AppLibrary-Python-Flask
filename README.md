# Despliegue automático para aplicación Flask con Gunicorn y Nginx

Este repositorio contiene scripts en Bash y Python que automatizan la instalación y configuración de un entorno completo para ejecutar una aplicación Flask utilizando Gunicorn como servidor de aplicaciones y Nginx como proxy inverso.

## Script en Bash (`upPython3.sh`) -> En el repo está como upPython3.txt (asegurarse de brindar permisos de ejecución sobre usuario)

Este script se encarga de:

1. **Detectar el sistema operativo y su versión:** Realiza validaciones para asegurar la compatibilidad con el script.
2. **Verificar la instalación de Python 3:** Si Python 3 no está instalado y la versión del sistema operativo lo permite, procede con la instalación utilizando el comando adecuado para la distribución Linux detectada.

## Script en Python (`Script-Python.py`) -> En el repo está como Script-Python.txt (ejecutarlo con sudo)

Este script realiza las siguientes tareas:

1. **Verificar e instalar dependencias:** Verifica si `python3-pip`, `python3-venv`, `git` y `nginx` están instalados. Si no lo están, los instala.
2. **Crear entorno virtual:** Crea un directorio para el proyecto (si no existe), crea un entorno virtual con `venv`, lo activa e instala las dependencias del proyecto desde el archivo `requirements.txt`.
3. **Clonar o actualizar repositorio:** Clona el repositorio del proyecto desde GitHub (o realiza un `pull` si ya existe) en la carpeta del proyecto.
4. **Configurar Gunicorn:** Instala Gunicorn y lo configura para ejecutar la aplicación Flask.
5. **Configurar Nginx:** Instala Nginx y lo configura como proxy inverso para mejorar el rendimiento y la seguridad de la aplicación.

## Uso

1. Clona este repositorio: `git clone -b booklibrary https://github.com/roxsross/devops-static-web.git`
2. Ejecuta el script de Bash: `./upPython3.sh` (requiere permisos de ejecución: `chmod +x upPython3.sh`)
3. Ejecuta el script de Python: `sudo python3 Script-Python.py`

## Requisitos

* Sistema operativo Linux (ejecutado en Ubuntu)
* Conexión a Internet

## Notas

* Asegúrate de configurar las variables globales en el script de Python, como el nombre del directorio del proyecto, la URL del repositorio de GitHub, etc.
* Este script está diseñado para simplificar la configuración inicial del entorno. Para un despliegue en producción, se recomienda realizar ajustes adicionales.

## Contribuciones

¡Las contribuciones son bienvenidas! Si encuentras errores o tienes sugerencias de mejora, no dudes en abrir un issue o enviar un pull request.
