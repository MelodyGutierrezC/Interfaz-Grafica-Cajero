# Interfaz-Grafica-Cajero
El programa permite a los usuarios registrarse, iniciar sesión, consultar su saldo, realizar depósitos, retiros, transferencias, y ver el historial de transacciones.
Utiliza las bibliotecas javax.swing para la interfaz grafica y java.io para la creacion de archivos, ademas de otras.

Descripción de Clases y Métodos

**Clase BancoLogix:**BancoLogix(): Constructor de la clase que configura la interfaz gráfica inicial.

**METODOS**

**-cargarUsuarios():** Lee los datos de los usuarios desde un archivo (usuarios.txt) y los carga en un mapa (Map<String, Usuario> usuarios).

**-registrar():** Permite registrar un nuevo usuario. Si el usuario no existe, solicita un nombre, contraseña y genera un número de cuenta.

**-guardarUsuarioEnArchivo(Usuario usuario):** Guarda la información de un nuevo usuario en usuarios.txt.

**-guardarTodosLosUsuarios():** Guarda toda la información de usuarios actualizada en usuarios.txt.

**-ingresar():** Valida el nombre de usuario y contraseña, y si son correctos, abre el menú principal.

**-abrirMenuPrincipal():** Cambia la interfaz gráfica para mostrar el menú principal con opciones de consulta y operaciones bancarias.

**-abrirVentanaSaldo():** Abre una ventana que muestra el saldo actual del usuario.

**-abrirVentanaDepositar():** Permite al usuario realizar un depósito.

**-abrirVentanaRetirar():** Permite al usuario retirar dinero de su cuenta.

**-abrirVentanaTransferencia():** Realiza transferencias de dinero entre cuentas.

**-abrirVentanaHistorial():** Muestra el historial de transacciones del usuario actual.

**-registrarHistorial(Usuario usuario, String tipoTransaccion, double cantidad):** Registra las transacciones realizadas por el usuario en un archivo de historial (historial_nombreUsuario.txt).

**-buscarUsuarioPorNumeroCuenta(String numeroCuenta):** Busca un usuario por su número de cuenta en el mapa de usuarios.

**Método main():**
Crea una instancia de BancoLogix y hace visible la ventana para que el usuario pueda interactuar con la interfaz gráfica.

**FUNCIONAMIENTO INICIAL**
El programa comienza con una ventana de inicio que permite al usuario iniciar sesión con su nombre de usuario y contraseña o registrarse.


![image](https://github.com/user-attachments/assets/802d86a8-b9fa-41ab-94f4-aa729fb65fc0)









**1.-Inicio de Sesión:**
Los datos de usuarios se cargan desde un archivo (usuarios.txt) y se almacenan en un HashMap.En caso de que el usuario ya este registrado podra ir directo al menu principal de lo contrario pasaria al segundo paso.

**2.-Registro de Usuarios:**
Si el usuario no existe, puede registrar un nuevo nombre de usuario y contraseña.
Se genera un número de cuenta único y se guarda en el archivo junto con un saldo inicial de 0.0.
También se crea un archivo de historial (historial_nombreUsuario.txt).

**3.-Menú Principal:**
Después de iniciar sesión, el usuario accede al menú principal con las siguientes opciones:

![image](https://github.com/user-attachments/assets/1494490b-3797-47d5-b276-e54ac623d7f3)

**-Consultar saldo:** Muestra el saldo disponible.

![image](https://github.com/user-attachments/assets/31ed8a7e-84cd-4660-839b-f9010137f852)










Se crea una ventana emergente (JFrame) donde se muestra el saldo del usuario actual,tambien contiene el boton para retornar al menu principal.

**-Depositar dinero:** Permite al usuario depositar el dinero que desee.

![image](https://github.com/user-attachments/assets/0bbfc891-9361-480f-be72-9c9ab6364b3e)







Se abre una ventana donde el usuario puede ingresar el monto que desea depositar.
El nuevo saldo se guarda en el programa como tambien en el archivo de historial.txt
Tambien contiene el boton para retornar al menu principal.

**-Retirar dinero:** Permite retirar un monto si el saldo es suficiente,caso contrario saldra "Saldo Insuficiente".





![image](https://github.com/user-attachments/assets/296da474-dbeb-4f05-9c44-edea8705a655)





Se abre una ventana donde el usuario puede ingresar el monto a retirar,donde el sistema verificara si el usuario tiene saldo suficiente.
El retiro se registra en el historial de transacciones.

**-Transferir dinero:** Transfiere dinero a otra cuenta si el número de cuenta es válido y el saldo es suficiente.



![image](https://github.com/user-attachments/assets/db07fcd0-dc71-4a97-a712-0913512923ee)







Se abre una ventana donde el usuario ingresa el número de cuenta destino y el monto a transferir,donde el sistema tambien verificara si la cuenta a la que dese depositar existe y si el saldo del usuario es suficiente, en caso de que sea correcto, el dinero se transfiere de la cuenta del usuario actual a la cuenta destino.
Se actualizan los saldos de cada cuenta y se registra la transacción en los historiales de ambos usuarios.

**-Ver historial:** Muestra el historial de todos los movimientos de la cuenta actual,ademas se guardara en un archivo.txt + nombre de usuario.

![image](https://github.com/user-attachments/assets/5b51b36e-4e0f-4608-b5a4-00ce83b632f0)


![image](https://github.com/user-attachments/assets/f4c048e0-2cfc-4c6f-8c13-37db57e5a06a)







Se abre una ventana con un área de texto (JTextArea) donde se muestra el historial de transacciones del usuario.El historial se carga desde un archivo de texto específico para cada usuario historial + nombre de usuario.txt
El usuario puede ver todas los movimientos realizados, como depositos, transferencias, retiros y saldo restante.

**Salir:** Cierra la aplicación.

