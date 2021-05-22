# Instalación Microsoft Exchange Server 2016

## Requisitos
1. [Virtualbox](https://www.virtualbox.org)
2. [Windows Server 2016](https://www.microsoft.com/es-xl/evalcenter/evaluate-windows-server-2016)
3. [Exchange Server 2016](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwj2xobGmdrwAhVKmK0KHVHiDN0QFjAAegQIAhAD&url=https%3A%2F%2Fwww.microsoft.com%2Fen-us%2Fdownload%2Fdetails.aspx%3Fid%3D57388&usg=AOvVaw321h9vVlI5oBfqDDKUoRnM)

## Requisitos Máquina virtual
1. Windows Server 2016
2. Tres discos duros virtuales:
    1. Un disco duro virtual de 100 GB para nuestro sistema operativo
    2. Un disco duro virtual de 100 GB para nuestros archivos logs transaccionales
    3. Un disco duro virtual de 200 GB para nuestra base de datos
3. RAM: 8GB
4. Controlador de dominio

## Creación máquina virtual
1. Clic en nueva
2. Escribir nombre de máquina

    ![](./images/vm-name.png)

    > Para este ejemplo el nombre de mi máquina será **SRV-EXCH**
3. En tipo seleccionamos **Microsoft Windows** y en versión elegimos **Windows 2016 (64-bit)**

    ![](./images/vm-type-version.png)

4. En **tamaño de memoria** elegimos 8 GB

    ![](./images/vm-ram.png)

5. En **Disco duro** seleccionamos la opción de **Crear un nuevo disco duro virtual ahora** y clic en **crear**

    ![](./images/vm-hdd.png)

6. Seleccionamos el tamaño del disco duro virtual
    
    ![](./images/vm-hdd-size.png)
    > En este ejemplo estoy seleccionado 100 GB

7. En **Tipo de archivo de disco duro** seleccionamos VDI
    
    ![](./images/vm-hdd-type.png)

8. En **Almacenamiento en disco duro físico** seleccionamos **Reservado dinámicamente** y clic en **Continuar**
    
    ![](./images/vm-hdd-storage.png)


## Agregar archivo .ISO a nuestra máquina virtual
1. Seleccionar nuestra máquia virtual a la que le vamos agregar nuestro archivo .ISO
2. Clic derecho y seleccionamos la opción de **Configuración**

    ![](./images/vm-configuration.png)

3. Clic en **Almacenamiento**

    ![](./images/vm-storage.png)

4. Clic en **Vacío** en el apartado de **Dispositivos de almacenamiento**

    ![](./images/vm-vacio.png)

5. Clic en el icono de **disco** para seleccionar un disco óptico virtual, seleccionamos la opción **Seleccionar un archivo de disco** y seleccionamos nuestro archivo .ISO de windows server 2016.

    ![](./images/vm-disco-optico.png)

## Agregar discos duros virtuales a nuestra máquina virtual
> :warning: En este ejemplo solo agregaremos dos discos duros virtuales ya que al momento de crear la máquina virtual hemos creado uno de 100 GB.
1. Seleccionar nuestra máquia virtual a la que le vamos agregar nuestros discos duros
2. Clic derecho y clic en **Configuración**

    ![](./images/vm-configuration.png)

3. Clic en **Almacenamiento**

    ![](./images/vm-storage.png)

4. Clic para agregar un nuevo disco duro virtual

    ![](./images/vm-new-vhd.png)

5. Clic en el botón de crear

    ![](./images/vm-create-vhd.png)

6. En el tipo de archivo de disco duro seleccionamos la opción VDI y damos clic en **siguiente**

    ![](./images/vm-vdi-vhd.png)

7. Seleccionamos **Reservado dinámicamente** y clic en **Continuar**

    ![](./images/vm-dinamic-vhd.png)

8. Seleccionamos el tamaño del disco duro virtual y clic en **Crear**
    
    ![](./images/vm-size-vhd.png)
    > En este ejemplo estoy seleccionado 100 GB

9. Una vez creado seleccionamos el disco duro virtual y damos clic en **Seleccionar**

    ![](./images/vm-select-vhd.png)

> :warning: Hacer el mismo procedimiento para agregar un disco duro virtual de 200 GB.

## Instalación windows server 2016
1. Clic en **Iniciar**

    ![](./images/vm-start.png)

2. Seleccionamos el tiempo y método de entrada del teclado

    ![](./images/vm-time.png)

3. Seleccionar **Windows Server 2016 Standard Evaluation (Desktop Experience)**

    ![](./images/vm-windows-de.png)

4. Aceptamos terminos de licencia
5. Selecionar opción **Personalizado**

    ![](./images/vm-custom.png)

6. Seleccionamos uno de los discos de 100 GB que agregamos previamente y damos clic en **Siguiente**

    ![](./images/vm-select-hdd.png)

7. Esperamos a que se instale el sistema operativo.
8. Agregamos un password y clic en **Terminar**

    ![](./images/vm-passwords.png)

## Configuración básica de nuestro servidor
1. Cambiar el nombre de nuestro servidor, abrir PowerShell y ejecutar el siguiente comando:
    ```powershell
    Rename-Computer -NewName "SRV-EXCH"
    ```
    Después de ejecutar el comando, ejecutar el siguiente comando para reiniciar nuestro servidor
    ```powershell
    Restart-Computer
    ```
2. Configuración de red de nuestro servidor
    |||
    |----|----|
    |IP address|192.168.0.10|
    |Mascara de subred|255.255.255.0|
    |Puerta de enlace predeterminada|192.168.0.1|
    |Servidor DNS|192.168.0.10|
3. Instalar ADDS
    1. Clic en **agregar roles y caracteristicas**
        ![](./images/vm-add-role.png)
    2. Clic en siguiente
    3. Seleccionamos la opción **Instalación basada en funciones** y clic en siguiente
        ![](./images/vm-rolebased.png)
    4. Seleccionamos el servidor y clic en siguiente
        ![](./images/vm-serverpool.png)
    5. Seleccionamos el rol de **Active Directory Domain Services**, damos clic en **Agregar caracteristicas** y clic en siguiente
        ![](./images/vm-adds-role.png)
    6. Clic en siguiente
    7. Clic en instalar
        ![](./images/vm-adds-install.png)


