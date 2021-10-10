# Documentation

## Instalación Kali y Parrot- OVA
- En primer lugar, nos dirigmos a dónde aparece **Import** y seleccionamos nuestra OVA.

![[ImportKali.png]](/Images/ImportKali.png)

![[selectOva.png]](/Images/selectOva.png)

- Le damos a **Next**  y especificamos las características que queramos que tenga la máquina. A continuación voy a dejar mis características por si queréis tomar la misma configuración:
	- *CPU : 4*
	- *RAM: 2048*
	- *Network:  Bridge* (esta opción la pondremos cuando se instale la OVA).

- Esperamos que se instale...


![[Installing.png]](/Images/Installing.png)

- Una vez instalado, nos dirigimos a **Settings** y en la sección **Network** la cambiamos **NAT** por **Bridge Adapter**.

![[SettingsBridgeAdapter.png]](/Images/SettingsBridgeAdapter.png)

- Una vez tengamos la configuración como hemos indicado, pulsamos en **Start** para comenzar con la *instalacion - configuración*.

## Configuración Kali

Si nos hemos descargado la OVA de la web oficial, el **user y password** es *kali:kali*. 

Una vez dentro, abrimos la terminal con **click derecho - Open terminal here** o en la parte superior del escritorio.

![[openTerminal.png]](/Images/openTerminal.png)

A continuación, vamos a realizar una actualización de los paquetes y descarga de los mismos. No sin antes comprobar que tenemos conexión a internet, para ello vamos a escribir el siguiente comando:

```
ping www.google.es
or
ping 8.8.8.8
```

```ad-note
**Ping es un comando o una herramienta de diagnóstico** que permite hacer una **verificación del estado de una determinada conexión de un host local** con al menos un equipo remoto contemplado en una **red de tipo TCP/IP.**

**Sirve para determinar si una dirección IP específica o host es accesible desde la red o no**.

```

![[Talleres/1 Taller - Configuracion-Instalacion Parrot/Images/pingGoogle.png]](/Images/pingGoogle.png)

Comprobamos como efectivamente nos responde y por tanto, **tenemos conexión** a internet.

Ahora vamos con la **actualización y descarga de paquetes**:

```
sudo apt update && sudo apt upgrade
```

![[aptUpdateUpgrade.png]](/Images/aptUpdateUpgrade.png)

Escribimos **Y** y pulsamos enter o directamente pulsamos **enter** ya que por defecto nos instalará todos los paquetes.

![[restartlibs.png]](/Images/restartlibs.png)

```ad-warning
**LA ACTUALIZACIÓN DE PAQUETES REALIZARLA DESDE CASA CON VUESTRA FIBRA.** Es un proceso que suele tardar bastante.
```

## Configuración Parrot

Si nos hemos descargado la OVA de la web oficial, **NO** tendremos que proporcionar **user y password**. Aunque una vez dentro el usuario y password son **user** y **toor**.

![[errorParrot.png]](/Images/errorParrot.png)

```ad-note
Puede que cuando arranquemos la máquina nos salga este error. Para solucionarlo nos vamos a la terminal y escribimos **sudo modprobe vboxdrv**
```

Una vez dentro, abrimos la terminal con **click derecho - Open in terminal**  o en la parte superior del escritorio.

A continuación, vamos a realizar una actualización de los paquetes y descarga de los mismos. No sin antes comprobar que tenemos conexión a internet, para ello vamos a escribir el siguiente comando:

```
ping www.google.es
or
ping 8.8.8.8
```

```ad-note
**Ping es un comando o una herramienta de diagnóstico** que permite hacer una **verificación del estado de una determinada conexión de un host local** con al menos un equipo remoto contemplado en una **red de tipo TCP/IP.**

**Sirve para determinar si una dirección IP específica o host es accesible desde la red o no**.

```
![[pingGoogleParrot.png]](/Images/pingGoogleParrot.png)

Comprobamos como efectivamente nos responde y por tanto, **tenemos conexión** a internet.

Ahora vamos con la **actualización y descarga de paquetes**:

```
sudo apt update && sudo parrot-upgrade
```

```ad-warning
En parrrot no es **apt upgrade**, cuidado porque nos podemos cargar el gestor de paquetes. En parrot es **parrot-upgrade**.
```

```ad-warning
**LA ACTUALIZACIÓN DE PAQUETES REALIZARLA DESDE CASA CON VUESTRA FIBRA.** Es un proceso que suele tardar bastante.
```

## Manejo por la terminal

Una vez abierta la terminal, lo que nos encotramos es el **Prompt**, que nos proporciona información como nuestro **usuario** el **host** y el **directorio actual** donde nos encontramos.

![[prompt.png]](/Images/prompt.png)

- **user** es el nombre de usuario de nuestro equipo con el que tenemos la sesión iniciada.
- **parrot** pertenece al host del sistema.
- **~/Desktop** pertenece a la ruta donde nos encontramos

```ad-note
La ~ virgulilla corresponde a la ruta del home de nuestro usuario, es decir, en el caso de la imagen anterior correspondería a /home/user/. Por tanto ~ = /home/user/
```

### Comandos básicos

| Comandos | Significado                 | Objetivo                                       |
| -------- | --------------------------- | ---------------------------------------------- |
| pwd      | Print Working Directory     | Imprimero el directorio actual de trabajo      |
| ls       | Listing                     | Lista ficheros y directorios                   |
| cd       | Change to another Directory | Cambiar de directorio                          |
| mkdir    | Make Directory              | Crear direcotorios                             |
| rmdir    | Remove Directory            | Eliminar directorios (empty)                   |
| touch    |                             | Crear fichero/s (empty)                        |
| echo “ ” |                             | Imprimir cadenas de string                     |
| cp       | Copy                        | Copiar ficheros y directorios                  |
| mv       | Move                        | Mover ficheros - directorios y cambiar nombres |
| cat      | Con**ca**tenate             | Leer, crear y escribir ficheros                |
| grep     |                             | Buscar texto en un fichero                                               |

#### Ejercicio - Manejo de la terminal
**1.** Sitúate en el directorio "_Escritorio_"  
  
**2.** Crea un directorio llamado "_Ejercicio_"  
  
**3.** Sin moverte del Escritorio, crea un fichero llamado _fichero.txt_ dentro del directorio que acabas de crear (_Ejercicio_)  
  
**4.** Ahora sitúate en el directorio "_Ejercicio_"  
  
**5.** Usando un solo comando, crea los ficheros _a.txt, b.txt_ y _c.txt_  
  
**6.** Usando un solo comando, borra los ficheros _b.txt_ y _c.txt_  
  
**7.** Sitúate en el directorio padre ("_Escritorio_")  
  
**8.** Usando un único comando, borra el directorio "_Ejercicio_" y todo su contenido

### Más sobre los comandos
Si queremos crear un directorio con espacio no podemos hacerlo de la siguiente forma:

```
mkdir Hello World
```

Ya que de este modo se intepretaría que queremos crear dos directorios, uno llamo *Hello* y otro *World*. Si queremos crear un directorio con espacio tenemos dos opciones:

```
mkdir "Hello World"
mkdir Hello\ World
```

Lo mismo pasaría con el comando **touch**.

Por otro lado tenemos el comando **ls** que trae con él bastantes opciones interesantes como son **-a** y **-l**:

- **-a -all** No oculta los ficheros que sean ocultos.
- **-l** utiliza un foramto de listado largo (long).

![[ls-l.png]](/Images/ls-l.png)

## Instalación del zsh

### Descarga de las Hack Nerd Fonts

- Nos vamos a [NerdFonts](https://www.nerdfonts.com/), y hacemos clic donde dice **Fonts Downloads**.

![[nerdFonts.png]](/Images/nerdFonts.png)

- Buscamos por **Hack Nerd Font** y descargamos el .zip.

![[hackNerdFonts.png]](/Images/hackNerdFonts.png)

- Movemos **Hack.zip** a la ruta **/usr/local/share/fonts**.

```
sudo mv Hack.zip /usr/local/share/fonts
```

![[mvHackZip.png]](/Images/mvHackZip.png)

- Nos dirigimos a la ruta a la que hemos movido el fichero **Hack.zip** y los descomprimimos con **unzip fichero**.

```
sudo unzip Hack.zip
```

![[unzipHack.png]](/Images/unzipHack.png)

- Ya podemos eliminar el zip.

```
sudo rm Hack.zip
```

- Nos dirigimos en la parte superior de la terminal donde aparece **Edit -> Profile Preferences**.

![[editProfile.png]](/Images/editProfile.png)

- Una vez dentro deseleccionamos la opción *Use the system fixed width font* y en **Font** buscamos y seleccionamos **Hack Nerd Font Mono Regular**. Por último salimos para guardar la configuración.

![[MonoRegular.png]](/Images/MonoRegular.png)

### Descarga y configuración de powerlevel10k

- Accedemos al siguiente enlace [Powerlevel10k](https://github.com/romkatv/powerlevel10k).

- Filtramos por **Installation**, copiamos y pegamos lo que aparece en la imagen en nuestra terminal.

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```

![[powerLevel10k.png]](/Images/powerLevel10k.png)

- Una vez clonado ya podemos ejecutar **zsh** para su configuración. Escribimos en la terminal **zsh** y realizamos la configuración.

```
zsh
```

![[inicioZsh.png]](/Images/inicioZsh.png)

![[instaladaPowerLevel10k.png]](/Images/instaladaPowerLevel10k.png)

- Una vez instalada la pw10k, vamos a proceder a la configuración de la misma. Para ello nos dirigimos a la ruta **~/.p10.zsh** y lo abrimos con el editor nano.

```
nano ~/.p10k.zsh
```

- Si queréis tener la misma configuración que la mía debéis de dejarlo de la siguiente manera:

![[derechaPW10k.png]](/Images/derechaPW10k.png)

- Tenéis que comentar todas las líneas que aparecen en la imagen, es decir, todas aquellas que correspondan a los elementos que nos aparecen a la derecha del **Prompt**.
- Y dejar la izquierda del Prompt de la siguiente manera:

![[izquierdaPW10k.png]](/Images/izquierdaPW10k.png)

- Con **status** nos reconoce si los comandos que escribamos tienen un estado exitoso o erróneo.
- Con **context** nos muestra cuál es el código de ese estado.
- Con **command_execution_time** nos muestra el tiempo que se demoró en realizar cualquier acción.

Ahora deberíamos de hacer el mismo proceso que hemos hecho con **root** ya que es otro usuario del sistema.

```ad-warning
Root tiene su propio directorio home, para irnos a él con sólo escribit **cd** nos bastaría.
```

![[rootP10k.png]](/Images/rootP10k.png)

- Volvemos a ir al archivo de configuración **p10k.zsh** y lo dejamos igual que nuestro usuario.

Una vez guardado el fichero nos salimos, cerramos la terminal, volvemos a abrirla, accedemos como **root** y escribimos **zsh**.

![[rootZsh.png]](/Images/rootZsh.png)

Vamos a cambiar el texto por un icono para que no nos ocupe tanto espacio y quede más cool xD.

- Para ello accedemos al **p10k.zsh** de root y nos filtramos por **ROOT_TEMPLATE**.

![[FiltrarRootTemplate.png]](/Images/FiltrarRootTemplate.png)

![[CAMBIARRoot.png]](/Images/CAMBIARRoot.png)

- Entre las comillas vamos a poner nuestro icono que queramos que aparezca, para ello nos vamos a la página **Nerd Fonts** y damos en **Icons**.

![[Icons.png]](/Images/Icons.png)

Buscamos el que nos guste y le damos a **Icon** para copiarlo.

![[iconos.png]](/Images/iconos.png)

Nos dirigimos al texto que queríamos cambiar por el icono y lo sustituimos.

![[iconRoot.png]](/Images/iconRoot.png)

- Guardamos, cerramos la terminal, abrimos de nuevo, accedemos al usuario root y escribimos zsh.

![[AndroidRoot.png]](/Images/AndroidRoot.png)

Ya vemos nuestro icono configurado correctamente!! Ahora bien, vamos a ver cómo establecer la **zsh** como la shell por defecto en vez de **bash** para no tener que escribir siempre **zsh** para usarla.

### Crear enlace simbólico del zshrc

Para no tener que cambiar el fichero **.zshrc** tanto para el usuario root como para nuestro usuario, vamos a crear un enlace simbólico. Para ello, siendo **root** y estando en el directorio home de root, escribimos lo siguiente:

```
cd /root
ln -s -f /home/user/.zshrc .zshrc
```

![[enlaceSimbolico.png]](/Images/enlaceSimbolico.png)

Ahora cada vez que hagamos cualquier cambio en nuestro **user**, cambiará en el de root también.

Vamos a quitar el *Welcome to Parrot* que aparece cuando entramos en la zsh.

![[quitarWelcome.png]](/Images/quitarWelcome.png)

### Cambiar la Shell de Bash a Zsh

Si nos fijamos con : ``` cat /etc/passwd | grep -E '^root|^user'``` vemos que tenemos una **/bin/bash**. 

Para cambiarla escribimos los siguientes comandos:

```
usermod --shell /usr/bin/zsh root
usermod --shell /usr/bin/zsh user
reboot
```

![[zshInstalada.png]](/Images/zshInstalada.png)

Ya lo tenemos todo correctamente funcionando, además esta **zsh** nos trae con un predictor inteligente.

#### Evitar problema de permisos
Para evitar un problema de permisos a la hora de que el usuario **root** quiera migrar son ´su´ al usuario con bajos privilegios, ejecutamos los siguientes comandos:

```
chown user:user /root
chown user:user /root/.cache -R
chown user:user /root/.local -R
```

### Instalar plugins para la terminal

#### BAT
Con bat veremos un output mucho más estético, para ello buscamos **bat github** en google y nos vamos al primer resultado. Posteriormente nos dirigimos a los **releases** y nos descargamos de la última versión el **deb**

![[BAT1.png]](/Images/BAT1.png)

![[BAT2.png]](/Images/BAT2.png)

![[BAT3.png]](/Images/BAT3.png)

Una vez descargado, lo tenemos que instalar:

```
cd Downloads/
sudo dpkg -i bat_0.18.3_amd64.deb
```

Ahora si escribimos **bat /etc/hosts** lo veremos de la siguiente manera:

![[batdesign.png]](/Images/batdesign.png)

Vemos que es mucho más bonito. Ahora vamos a agregar un alias para que el **cat** nos lo detecte como **bat**. Para ello nos vamos al *.zshrc* y creamos lo siguiente:

![[aliases.png]](/Images/aliases.png)

Si cerramos la terminal y volvemos a abrirla, veremos que se ejecuta el **bat** correctamente:

![[catETCHOSTS.png]](/Images/catETCHOSTS.png)

### Tarea

- Realizar lo mismo con el **lsd** y aplicarle unos alias en el **.zshrc**.


#### Solution: Aliases lsd

```
alias ll='lsd -lh --group-dirs=first'
alias la='lsd -a --group-dirs=first'
alias l='lsd --group-dirs=first'
alias lla='lsd -lha --group-dirs=first'
alias ls='lsd --group-dirs=first'
```

## OverTheWire

Realizar los 7 primeros ejercicios.
