## Fase II: Diseño del Sistema

# Listado de Sustantivos → Clases del Sistema

# Sustantivos identificados del enunciado:

-Usuario

-Acceso

-Registro

-Control

-Seguridad

-Empresa

-Trabajador

-Sistema

# Clases identificadas del código:

-Usuario - Representa a un trabajador de la empresa

-RegistroAcceso - Representa un registro de ingreso/salida

-InterfazPrincipal - Control principal del sistema

-GestorArchivos - Maneja la persistencia de datos

-RegistroUsuario - Interfaz para registrar usuarios

-EliminarUsuario - Interfaz para eliminar usuarios

-IngresoUsuario - Interfaz para registrar ingresos

-SalidaUsuario - Interfaz para registrar salidas

-Licencia - Interfaz de términos y condiciones

Main - Punto de entrada de la aplicación


<img width="3311" height="3673" alt="Image" src="https://github.com/user-attachments/assets/5da76aa5-c84a-40ae-b6fb-256d805cce76" />


| Clase             | Atributo         | Codificación       | Objetivo                                                     |
|-------------------|------------------|---------------------|--------------------------------------------------------------|
| Usuario           | id               | id                  | Identificador único del usuario (formato 11AA11)            |
| Usuario           | nombre           | nombre              | Nombre del trabajador                                        |
| Usuario           | apellido         | apellido            | Apellido del trabajador                                      |
| RegistroAcceso    | idUsuario        | idUsuario           | ID del usuario que realiza el acceso                         |
| RegistroAcceso    | tipoAcceso       | tipoAcceso          | Tipo de acceso ("INGRESO" o "SALIDA")                       |
| RegistroAcceso    | fechaHora        | fechaHora           | Fecha y hora del registro automático                         |
| InterfazPrincipal | usuarios         | usuarios            | Lista de usuarios registrados en el sistema                  |
| InterfazPrincipal | registros        | registros           | Lista histórica de registros de acceso                       |
| GestorArchivos    | ARCHIVO_USUARIOS | ARCHIVO_USUARIOS    | Nombre del archivo para persistir usuarios                   |
| GestorArchivos    | ARCHIVO_REGISTROS| ARCHIVO_REGISTROS   | Nombre del archivo para persistir registros                  |

