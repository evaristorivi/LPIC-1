# Tema 105: Shells y scripts

## 105.1 Personalizar y usar el entorno de shell

Setting Up the Shell Environment

---

Customizing the Shell Environment

## 105.2 Personalización y escritura de scripts sencillos

 Basic Shell Scripts

 ---
 
 Adding Logic to Your Shell Scripts
 
 ----

  Bash Loops and Sequences

`for` -


`while` -

`until` -

---

`read` Leemos lo que introducimos por teclado y lo guardamos en la variable GRETTING. `read GREETING`.

`exit` - para especificar el retorno de salida, normalmente seria 0, pero se puede cambiar a otro numero, por ejemplo para salir en un bucle.

`exec` - se puede utilizar para re-direccionar la salida de una shell a un fichero. `exec > out .log`
  ---


## 106: Interfaces de usuario y escritorios

### 106.1 Instalar y configurar X11

#### 106.1.1 The Basics of X11
X11 lo llevan los antiguos sistemas (CentOS 5)
Wayland - remplaza al sistema de ventas X. 

#### 106.1.2 Instalando X11

`yum grouplist` - para ver los grupos de instalaciones.

`yum -y groupinstall "X Windows System"`

x.org se encarga de llevar el proyecto.

Podemos encontrar el fichero de configuración en `/etc/init` y veremos que apunta a `/etc/X11/prefdm` 

#### 106.1.3 Configuraciones de X11

`xorg.conf` - fichero de configuración de entorno visual de ventanas X

man `xorg,conf` - para ver toda la documentación sobre la configuración del entorno de ventanas.

`xdpyinfo` - muestra información sobre la sesión de ventanas. 

### 106.1.4 Conexiones gráficas remotas

`xhost` - no usar para entornos de producción. (Se usaba antes) Con este comando podemos habilitar o deshabilitar el acceso remoto. 

```console
sergio@Lenovo-ideapad-710S-Plus-13IKB  ~  xhost             
access control enabled, only authorized clients can connect
SI:localuser:sergio
 sergio@Lenovo-ideapad-710S-Plus-13IKB  ~  xhost -
access control enabled, only authorized clients can connect
 sergio@Lenovo-ideapad-710S-Plus-13IKB  ~  xhost +
access control disabled, clients can connect from any host
```

`xauth` - sirve para editar y ver información de seguridad que permita a los usuarios controlar los clientes de ventanas X11.

`VNC` - Virtual Network computing.

Instalar el servidor de VNV:

`yum install tigervnc-server`


`SPICE` - Protocolo de conexion seguro encriptado con TLS, permite conexoines con sistemas Windows, linux y android.
