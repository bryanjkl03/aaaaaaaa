## Fase II: Diseño del Sistema

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

-Main - Punto de entrada de la aplicación


<table border="1" cellspacing="0" cellpadding="6" style="border-collapse: collapse; width:300px; text-align:left;">
  <tr>
    <th style="background:#f2f2f2; text-align:center;">Main</th>
  </tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - ninguno
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + main(String[] args): void
    </td>
  </tr>
</table>



| Clase             | Atributo         | Codificación       | Objetivo                                                     |
|-------------------|------------------|---------------------|--------------------------------------------------------------|
| Usuario           | id               | string                  | Identificador único del usuario (formato 11AA11)            |
| Usuario           | nombre           | string              | Nombre del trabajador                                        |
| Usuario           | apellido         | string            | Apellido del trabajador                                      |
| RegistroAcceso    | idUsuario        | string           | ID del usuario que realiza el acceso                         |
| RegistroAcceso    | tipoAcceso       | string          | Tipo de acceso ("INGRESO" o "SALIDA")                       |
| RegistroAcceso    | fechaHora        | date           | Fecha y hora del registro automático                         |
| InterfazPrincipal | usuarios         | List<Usuario>            | Lista de usuarios registrados en el sistema                  |
| InterfazPrincipal | registros        | List<RegistroAcceso>          | Lista histórica de registros de acceso                       |
| GestorArchivos    | ARCHIVO_USUARIOS | string    | Nombre del archivo para persistir usuarios                   |
| GestorArchivos    | ARCHIVO_REGISTROS| string   | Nombre del archivo para persistir registros                  |
| RegistroUsuario    | campoNombre| JTextField   | Campo para nombre usuario                  |
| RegistroUsuario    | 	campoApellido| JTextField   | Campo para apellido usuario                  |
