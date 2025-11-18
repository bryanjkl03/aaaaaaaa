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



<table border="1" cellspacing="0" cellpadding="6" style="border-collapse: collapse; width:350px;">
  <tr><th style="background:#f2f2f2; text-align:center;">InterfazPrincipal</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - listaUsuarios: JList<br>
      - modeloLista: DefaultListModel<br>
      - btnRegistrar: JButton<br>
      - btnEliminar: JButton<br>
      - btnIngreso: JButton<br>
      - btnSalida: JButton<br>
      - btnRegistro: JButton<br>
      - btnLicencia: JButton<br>
      - usuarios: List&lt;Usuario&gt;<br>
      - registros: List&lt;RegistroAcceso&gt;
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + InterfazPrincipal()<br>
      + inicializarComponentes(): void<br>
      + cargarDatos(): void<br>
      + actualizarListaUsuarios(): void<br>
      + actionPerformed(ActionEvent): void<br>
      + mostrarRegistros(): void<br>
      + agregarUsuario(Usuario): void<br>
      + eliminarUsuario(String): boolean<br>
      + buscarUsuario(String): Usuario<br>
      + agregarRegistro(RegistroAcceso): void<br>
      + getUsuarios(): List&lt;Usuario&gt;<br>
      + getRegistros(): List&lt;RegistroAcceso&gt;<br>
      + puedeIngresar(String): boolean<br>
      + puedeSalir(String): boolean
    </td>
  </tr>
</table>

<table border="1" cellspacing="0" cellpadding="6" style="border-collapse: collapse; width:300px;">
  <tr><th style="background:#f2f2f2; text-align:center;">Usuario</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - id: String<br>
      - nombre: String<br>
      - apellido: String
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + Usuario(String, String, String)<br>
      + getId(): String<br>
      + getNombre(): String<br>
      + getApellido(): String<br>
      + getIniciales(): String<br>
      + toString(): String
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:300px;">
  <tr><th style="background:#f2f2f2; text-align:center;">RegistroAcceso</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - idUsuario: String<br>
      - tipoAcceso: String<br>
      - fechaHora: Date
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + RegistroAcceso(String, String)<br>
      + getIdUsuario(): String<br>
      + getTipoAcceso(): String<br>
      + getFechaHora(): Date<br>
      + getFechaHoraFormateada(): String<br>
      + toString(): String
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:350px;">
  <tr><th style="background:#f2f2f2; text-align:center;">GestorArchivos</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - ARCHIVO_USUARIOS: String<br>
      - ARCHIVO_REGISTROS: String
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + guardarUsuarios(List&lt;Usuario&gt;): void<br>
      + cargarUsuarios(): List&lt;Usuario&gt;<br>
      + guardarRegistros(List&lt;RegistroAcceso&gt;): void<br>
      + cargarRegistros(): List&lt;RegistroAcceso&gt;<br>
      + generarIdUnico(List&lt;Usuario&gt;): String<br>
      + tieneIngresoPendiente(String, List&lt;RegistroAcceso&gt;): boolean<br>
      + puedeIngresar(String, List&lt;RegistroAcceso&gt;): boolean<br>
      + puedeSalir(String, List&lt;RegistroAcceso&gt;): boolean
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:330px;">
  <tr><th style="background:#f2f2f2; text-align:center;">RegistroUsuario</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - campoNombre: JTextField<br>
      - campoApellido: JTextField<br>
      - btnAceptar: JButton<br>
      - btnCancelar: JButton<br>
      - interfazPrincipal: InterfazPrincipal
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + RegistroUsuario(InterfazPrincipal)<br>
      + inicializarComponentes(): void<br>
      + actionPerformed(ActionEvent): void<br>
      + registrarUsuario(): void
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:320px;">
  <tr><th style="background:#f2f2f2; text-align:center;">EliminarUsuario</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - campoId: JTextField<br>
      - btnEliminar: JButton<br>
      - btnCancelar: JButton<br>
      - interfazPrincipal: InterfazPrincipal
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + EliminarUsuario(InterfazPrincipal)<br>
      + inicializarComponentes(): void<br>
      + actionPerformed(ActionEvent): void<br>
      + eliminarUsuario(): void
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:320px;">
  <tr><th style="background:#f2f2f2; text-align:center;">IngresoUsuario</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - campoId: JTextField<br>
      - btnIngresar: JButton<br>
      - btnCancelar: JButton<br>
      - interfazPrincipal: InterfazPrincipal
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + IngresoUsuario(InterfazPrincipal)<br>
      + inicializarComponentes(): void<br>
      + actionPerformed(ActionEvent): void<br>
      + registrarIngreso(): void
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:320px;">
  <tr><th style="background:#f2f2f2; text-align:center;">SalidaUsuario</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - campoId: JTextField<br>
      - btnSalida: JButton<br>
      - btnCancelar: JButton<br>
      - interfazPrincipal: InterfazPrincipal
    </td>
  </tr>
  <tr>
    <td>
      <strongMétodos</strong><br>
      + SalidaUsuario(InterfazPrincipal)<br>
      + inicializarComponentes(): void<br>
      + actionPerformed(ActionEvent): void<br>
      + registrarSalida(): void
    </td>
  </tr>
</table>


<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width:260px;">
  <tr><th style="background:#f2f2f2; text-align:center;">Licencia</th></tr>
  <tr>
    <td>
      <strong>Atributos</strong><br>
      - areaTexto: JTextArea
    </td>
  </tr>
  <tr>
    <td>
      <strong>Métodos</strong><br>
      + Licencia()<br>
      + inicializarComponentes(): void
    </td>
  </tr>
</table>



## Documentacion atributos de la clase
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
