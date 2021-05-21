# Instalación Microsoft Exchange Server 2016

## Requisitos
1. [Virtualbox](https://www.virtualbox.org)
2. [Windows Server 2016](https://www.microsoft.com/es-xl/evalcenter/evaluate-windows-server-2016)
3. [Exchange Server 2016](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwj2xobGmdrwAhVKmK0KHVHiDN0QFjAAegQIAhAD&url=https%3A%2F%2Fwww.microsoft.com%2Fen-us%2Fdownload%2Fdetails.aspx%3Fid%3D57388&usg=AOvVaw321h9vVlI5oBfqDDKUoRnM)

## Requisitos Máquina virtual
1. [Windows Server 2016](https://www.microsoft.com/es-xl/evalcenter/evaluate-windows-server-2016)
2. Tres discos duros:
    1. Un disco duro de 100 GB para nuestro sistema operativo
    2. Un disco duro de 100 GB para nuestros archivos logs transaccionales
    3. Un disco duro de 200 GB para nuestra base de datos
3. RAM: 8GB
4. Controlador de dominio

## Creación máquina virtual
1. Clic en nueva
2. Escribir nombre de máquina
    ![]()
    > Para este ejemplo el nombre de mi máquina será **SRV-EXCH**
3. En tipo seleccionamos **Microsoft Windows** y en versión elegimos **Windows 2016 (64-bit)**
    ![]()
4. En **tamaño de memoria** elegimos 8 GB
    ![]()
5. En **Disco duro** seleccionamos la opción de **Crear un nuevo disco duro virtual ahora** y clic en **crear**
    ![]()
6. En **Tipo de archivo de disco duro** seleccionamos VDI y clic en **Continuar**
    ![]()
7. En **Almacenamiento en disco duro físico** seleccionamos **Asignado dinámicamente** y clic en **Continuar**
    ![]()
8. Seleccionamos el tamaño del disco duro y clic en **crear**
    ![]()
    > En este ejemplo estoy seleccionado 100 GB

## Agregar archivo .ISO a nuestra máquina virtual
1. Seleccionar nuestra máquia virtual a la que le vamos agregar nuestro archivo .ISO
2. Clic derecho y clic en **configuraciones**
3. Clic en **storage**
4. Clic en el apartado de **disk image file**
5. Clic en **eEige un disco óptico virtual**
6. Clic en la opción **Escoger archivo de disco** y seleccionamos nuestro archivo .ISO



## Agregar discos duros a nuestra máquina virtual
1. Seleccionar nuestra máquia virtual a la que le vamos agregar nuestros discos duros
2. Clic derecho y clic en **configuraciones**
3. Clic en **storage**