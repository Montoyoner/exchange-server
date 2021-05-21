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

8. En **Almacenamiento en disco duro físico** seleccionamos **Asignado dinámicamente** y clic en **Continuar**
    
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
2. Clic derecho y clic en **configuraciones**
3. Clic en **storage**