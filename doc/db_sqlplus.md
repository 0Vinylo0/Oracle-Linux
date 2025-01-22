# Instalación de Oracle Database XE y SQL\*Plus

## Instalación de Oracle Database XE

1. Descargue Oracle Database Express Edition (XE) desde el [sitio oficial de Oracle](https://www.oracle.com/database/technologies/appdev/xe.html).

<image src="img/Captura desde 2025-01-17 10-15-10.png">

2. Transfiera el archivo descargado al sistema Oracle Linux.

3. Instale el paquete RPM:

   ```bash
   sudo dnf install -y /ruta/al/archivo.rpm
   ```

<image src="img/Captura desde 2025-01-17 11-14-15.png">


4. Configure Oracle Database XE ejecutando el siguiente comando:

   ```bash
   sudo /etc/init.d/oracle-xe-21c configure
   ```

<image src="img/Captura desde 2025-01-22 09-33-24.png">

   Siga las instrucciones para establecer un puerto de escucha y una contraseña para el usuario SYS/SYSTEM.

5. Verifique que el servicio esté en ejecución:

   ```bash
   sudo systemctl status oracle-xe-21c
   ```

## Instalación y Configuración de SQL\*Plus

1. Instale el cliente Oracle Instant Client:

   ```bash
   sudo dnf install -y oracle-instantclient-release-el8
   sudo dnf install -y oracle-instantclient-basic oracle-instantclient-sqlplus
   ```

2. Configure las variables de entorno:

   ```bash
   echo "export PATH=\$PATH:/usr/lib/oracle/<version>/client64/bin" >> ~/.bashrc
   echo "export LD_LIBRARY_PATH=/usr/lib/oracle/<version>/client64/lib" >> ~/.bashrc
   source ~/.bashrc
   ```

   > Reemplace `<version>` con la versión instalada del cliente Oracle.

3. Conéctese a la base de datos usando SQL\*Plus:

   ```bash
   sqlplus SYSTEM@localhost
   ```

   Introduzca la contraseña configurada durante la instalación de Oracle XE.

---

## Recursos Adicionales

- [Documentación Oficial de Oracle Linux](https://docs.oracle.com/en/operating-systems/)
- [Soporte de Oracle Linux](https://www.oracle.com/support/)
- [Documentación Oficial de Oracle Database XE](https://docs.oracle.com/en/database/)
