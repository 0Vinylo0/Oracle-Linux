# Guía de Instalación de Oracle Linux

## Introducción

### Oracle Linux
Oracle Linux es un sistema operativo empresarial basado en Linux, diseñado para ofrecer estabilidad, seguridad y rendimiento óptimo, especialmente en entornos empresariales y en la nube.

### Oracle Database
Oracle Database es un sistema de gestión de bases de datos relacional ampliamente utilizado. Su versión Express Edition (XE) es gratuita y ligera, ideal para aprender y desarrollar aplicaciones pequeñas.

Esta guía detalla cómo instalar Oracle Linux, configurar Oracle Database XE y utilizar SQL*Plus.

---

## Requisitos Previos

### Hardware Recomendado

- Procesador: x86\_64 compatible
- RAM: Mínimo 1 GB (recomendado 4 GB o más)
- Almacenamiento: Mínimo 10 GB de espacio libre en disco (50 GB recomendados)
- Conexión a Internet para descargas opcionales

### Software

- Imagen ISO de Oracle Linux (disponible en el [sitio oficial de Oracle Linux](https://www.oracle.com/linux/))

---

## Paso 1: Descarga de Oracle Linux

1. Acceda al [sitio oficial de Oracle Linux](https://www.oracle.com/linux/).
2. Navegue a la sección de descargas y seleccione la versión deseada de Oracle Linux.
3. Descargue la imagen ISO correspondiente a su arquitectura.

---

## Paso 2: Configuración del Entorno de Instalación

1. Arranque desde la imagen ISO descargada.
2. Seleccione la opción de instalación de Oracle Linux en el menú de inicio.

---

## Paso 3: Proceso de Instalación

### 1. Selección del Idioma

Seleccione el idioma y la distribución de teclado deseados y haga clic en **Continuar**.

### 2. Configuración de Instalación

En la pantalla principal:

- **Destino de Instalación**: Seleccione el disco donde instalará Oracle Linux.
  - Elija "Automático" para particionado automático o "Manual" para configuración personalizada.
- **Red y Nombre de Host**: Configure la red si desea que el sistema tenga conectividad desde el primer inicio.

### 3. Iniciar Instalación

Haga clic en **Comenzar Instalación**.

### 4. Configurar Usuarios

Mientras la instalación se ejecuta:

- Configure una contraseña para el usuario root.
- Cree un usuario adicional con privilegios administrativos.

---

## Paso 4: Primer Inicio

1. Reinicie el sistema.
2. Inicie sesión con el usuario configurado.

---

## Paso 5: Configuración Post-Instalación

### Actualización del Sistema

Ejecute los siguientes comandos para actualizar el sistema:

```bash
sudo dnf update -y
```

### Instalación de Herramientas Adicionales

Dependiendo del uso previsto, instale herramientas adicionales:

```bash
sudo dnf install -y vim nano wget curl git
```

### Habilitar Repositorios de Oracle

Habilite repositorios opcionales si es necesario:

```bash
sudo dnf config-manager --enable ol8_addons
```

---

## Recursos Adicionales

- [Documentación Oficial de Oracle Linux](https://docs.oracle.com/en/operating-systems/)
- [Soporte de Oracle Linux](https://www.oracle.com/support/)
