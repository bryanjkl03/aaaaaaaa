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

# Main
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


# interfaz principal
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


# Usuario
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

# RegistroAcceso
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

# GestorArchivos
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

# RegistroUsuario
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

# EliminarUsuario
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

# IngresoUsuario
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

# SalidaUsuario
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

# Licencia
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


# Fase III:
# Documentación Métodos de la clase

# Clase InterfazPrincipal


# InterfazPrincipal()
| Nombre del Método | InterfazPrincipal() |
|-------------------|---------------------|
| Entrada (lista de parámetros) | Ninguna |
| Resultado (tipo de dato de retorno) | Ninguno (constructor) |
| Solución planteada | Inicializa la interfaz principal del sistema y configura los componentes gráficos. |
| Firma del Método | public InterfazPrincipal() |


# inicializarComponentes()
| Nombre del Método | inicializarComponentes |
|-------------------|------------------------|
| Entrada (lista de parámetros) | Ninguna |
| Resultado (tipo de dato de retorno) | void |
| Solución planteada | Crea y configura todos los elementos visuales y botones de la interfaz. |
| Firma del Método | public void inicializarComponentes() |

# cargarDatos()
| Nombre del Método | cargarDatos |
|-------------------|-------------|
| Entrada | Ninguna |
| Resultado | void |
| Solución planteada | Carga desde archivo la lista de usuarios y registros almacenados. |
| Firma del Método | public void cargarDatos() |

# actualizarListaUsuarios()
| Nombre del Método | actualizarListaUsuarios |
|-------------------|-------------------------|
| Entrada | Ninguna |
| Resultado | void |
| Solución planteada | Actualiza visualmente la lista de usuarios en pantalla usando el modelo de lista. |
| Firma del Método | public void actualizarListaUsuarios() |

# actionPerformed(ActionEvent)
| Nombre del Método | actionPerformed |
|-------------------|-----------------|
| Entrada | ActionEvent e |
| Resultado | void |
| Solución planteada | Gestiona todas las acciones de botones y ejecuta la operación correspondiente. |
| Firma del Método | public void actionPerformed(ActionEvent e) |

# mostrarRegistros()
| Nombre del Método | mostrarRegistros |
|-------------------|------------------|
| Entrada | Ninguna |
| Resultado | void |
| Solución planteada | Muestra la ventana con el historial completo de registros de acceso. |
| Firma del Método | public void mostrarRegistros() |

# agregarUsuario(Usuario)
| Nombre del Método | agregarUsuario |
|-------------------|----------------|
| Entrada | Usuario u |
| Resultado | void |
| Solución planteada | Añade un nuevo usuario a la lista y actualiza su visualización. |
| Firma del Método | public void agregarUsuario(Usuario u) |

# eliminarUsuario(String)
| Nombre del Método | eliminarUsuario |
|-------------------|-----------------|
| Entrada | String id |
| Resultado | boolean |
| Solución planteada | Elimina un usuario según su ID y devuelve true si fue eliminado. |
| Firma del Método | public boolean eliminarUsuario(String id) |

# buscarUsuario(String)
| Nombre del Método | buscarUsuario |
|-------------------|---------------|
| Entrada | String id |
| Resultado | Usuario |
| Solución planteada | Busca un usuario en la lista por su ID y lo retorna. |
| Firma del Método | public Usuario buscarUsuario(String id) |

# agregarRegistro(RegistroAcceso)
| Nombre del Método | agregarRegistro |
|-------------------|-----------------|
| Entrada | RegistroAcceso r |
| Resultado | void |
| Solución planteada | Añade un nuevo registro de acceso al historial del sistema. |
| Firma del Método | public void agregarRegistro(RegistroAcceso r) |

# getUsuarios()
| Nombre del Método | getUsuarios |
|-------------------|-------------|
| Entrada | Ninguna |
| Resultado | List<Usuario> |
| Solución planteada | Devuelve la lista completa de usuarios registrados. |
| Firma del Método | public List<Usuario> getUsuarios() |

# getRegistros()
| Nombre del Método | getRegistros |
|-------------------|--------------|
| Entrada | Ninguna |
| Resultado | List<RegistroAcceso> |
| Solución planteada | Devuelve la lista completa de registros almacenados. |
| Firma del Método | public List<RegistroAcceso> getRegistros() |

# puedeIngresar(String)
| Nombre del Método | puedeIngresar |
|-------------------|---------------|
| Entrada | String idUsuario |
| Resultado | boolean |
| Solución planteada | Determina si el usuario puede registrar un ingreso según su último estado. |
| Firma del Método | public boolean puedeIngresar(String idUsuario) |

# puedeSalir(String)
| Nombre del Método | puedeSalir |
|-------------------|------------|
| Entrada | String idUsuario |
| Resultado | boolean |
| Solución planteada | Verifica si el usuario puede registrar una salida según su estado anterior. |
| Firma del Método | public boolean puedeSalir(String idUsuario) |

# Clase Usuario

# Usuario(String, String, String)

| Nombre del Método | Usuario |
| Entrada | String id, String nombre, String apellido |
| Resultado | Ninguno (constructor) |
| Solución planteada | Crea un usuario con sus datos básicos. |
| Firma del Método | public Usuario(String id, String nombre, String apellido) |


# getId()

| Nombre del Método | getId |
| Entrada | Ninguna |
| Resultado | String |
| Solución planteada | Retorna el ID del usuario. |
| Firma del Método | public String getId() |


# getNombre()

| Nombre del Método | getNombre |
| Entrada | Ninguna |
| Resultado | String |
| Solución planteada | Retorna el nombre del usuario. |
| Firma del Método | public String getNombre() |

# getApellido()

| Nombre del Método | getApellido |
| Entrada | Ninguna |
| Resultado | String |
| Solución planteada | Retorna el apellido del usuario. |
| Firma del Método | public String getApellido() |


# getIniciales()

| Nombre del Método | getIniciales |
| Entrada | Ninguna |
| Resultado | String |
| Solución planteada | Genera las iniciales del usuario. |
| Firma del Método | public String getIniciales() |

# toString()

| Nombre del Método | toString |
| Entrada | Ninguna |
| Resultado | String |
| Solución planteada | Retorna la representación en texto del usuario. |
| Firma del Método | public String toString() |

