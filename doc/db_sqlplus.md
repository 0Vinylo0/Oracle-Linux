# Instalación de Oracle Database XE y SQL\*Plus

## Instalación de Oracle Database XE

1. Descargue Oracle Database Express Edition (XE) desde el [sitio oficial de Oracle](https://www.oracle.com/database/technologies/appdev/xe.html).

<image src="/img/Captura desde 2025-01-17 10-15-10.png">

2. Transfiera el archivo descargado al sistema Oracle Linux.

3. Instale el paquete RPM:

   ```bash
   sudo dnf install -y /ruta/al/archivo.rpm
   ```

<image src="/img/Captura desde 2025-01-17 11-14-15.png">


4. Configure Oracle Database XE ejecutando el siguiente comando:

   ```bash
   sudo /etc/init.d/oracle-xe-21c configure
   ```

<image src="/img/Captura desde 2025-01-22 09-33-24.png">

   Siga las instrucciones para establecer un puerto de escucha y una contraseña para el usuario SYS/SYSTEM.

5. Verifique que el servicio esté en ejecución:

   ```bash
   sudo systemctl status oracle-xe-21c
   ```

## Instalación y Configuración de SQL\*Plus

1. Instale el cliente Oracle Instant Client:

   En esta version de oracle ya viene instalado sqlplus solo hay que añadirlo en el `bashrc`

2. Configure las variables de entorno:

   ```bash
   export PATH=/opt/oracle/product/21c/dbhomeXE/bin:$PATH
   export ORACLE_HOME=/opt/oracle/product/21c/dbhomeXE
   export PATH=$ORACLE_HOME/bin:$PATH
   export LD_LIBRARY_PATH=$ORACLE_HOME/lib:$LD_LIBRARY_PATH
   export ORACLE_SID=XE

   ```
   
   <image src="/img/Captura desde 2025-01-24 10-30-32.png">

3. Habilitamos los puertos en el firewall del servido de oralce

   ```bash
      sudo firewall-cmd --add-port=1521/tcp --permanent
      sudo firewall-cmd --reload
   ```

   <image src="/img/Captura desde 2025-01-24 10-30-45.png">

   <image src="/img/Captura desde 2025-01-24 10-31-02.png">

5. Conéctese a la base de datos usando SQL\*Plus:

   ```bash
   sqlplus SYSTEM@localhost
   ```

   <image src="/img/Captura desde 2025-01-24 12-34-43.png">

   Introduzca la contraseña configurada durante la instalación de Oracle XE.

---

## Recursos Adicionales

- [Documentación Oficial de Oracle Linux](https://docs.oracle.com/en/operating-systems/)
- [Soporte de Oracle Linux](https://www.oracle.com/support/)
- [Documentación Oficial de Oracle Database XE](https://docs.oracle.com/en/database/)
