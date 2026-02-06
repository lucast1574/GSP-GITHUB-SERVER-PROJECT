<div align="center">

# 🚀 GSP-GITHUB-SERVER-PROJECT 🌐

### *A streamlined collection of commands to transform GitHub Codespaces into powerful servers*

---

[![GitHub Codespaces](https://img.shields.io/badge/GitHub-Codespaces-brightgreen?style=for-the-badge&logo=github)](https://github.com/features/codespaces)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge)](https://opensource.org/licenses/Apache-2.0)

✨ **Fast** | 🛠️ **Simple** | 💻 **Cloud-Native**

---

</div>

## 📖 Descripción
Este proyecto permite desplegar servidores de Minecraft (Java Edition), Minecraft (Bedrock), Hytale y Terraria, Futuramente Ark y demas juegos en **GitHub Codespaces** utilizando **LinuxGSM**. Está optimizado para ejecutarse directamente como usuario `root` para evitar problemas de permisos y maximizar la velocidad de despliegue.

---
# 🧊 MINECRAFT JAVA 
## 🛠️ Guía de Instalación Paso a Paso

Sigue estos comandos en orden dentro de la terminal de tu Codespace:

### 1. Acceso Total (Root)
Para evitar restricciones de permisos y trabajar de forma directa:
```bash
sudo su -
```

### 2. Dependencias del Sistema
```bash
apt update && apt install -y curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat-openbsd lib32gcc-s1 lib32stdc++6 steamcmd
```

### 3. Instalaicion de Java

- Java 8 version antiguas < 1.16.5

```bash
apt install -y openjdk-8-jdk
```

- Java 17 para versiones 1.17 a 1.20.4

```bash
apt install -y openjdk-17-jdk
```

- Java 17 para versiones 1.20.5 y superiores

```bash
apt install -y openjdk-21-jdk
```

### 4. Configurar Directorio

```bash
mkdir -p /root/minecraft-server && cd /root/minecraft-server
```

### 5. Descargar LinuxGSM

```bash
curl -Lo mcserver [https://linuxgsm.sh/mcserver](https://linuxgsm.sh/mcserver) && chmod +x mcserver
```

### 6. Instalacion Automatica 

```bash
./mcserver auto-install --allow-root
```

## Playit

Para obtener una IP fija sin depender del proxy HTTP de GitHub:

```bash
curl -Lo playit [https://github.com/playitcloud/playit-agent/releases/latest/download/playit-linux-amd64](https://github.com/playitcloud/playit-agent/releases/latest/download/playit-linux-amd64) && chmod +x playit
./playit
```

## 🎮 Comandos de Gestión

### Iniciar

```bash
./mcserver start --allow-root
```

### Consola

```bash
./mcserver console
```

### Detener

```bash
./mcserver stop --allow-root
```

### Detalles

```bash
./mcserver details
```

## ⚙️ Configuración Extra

Argumentos Jvm

```bash
# Configuración de Memoria y Flags Optimizado para Codespaces
javaram="12288"
executable="./server.jar"
preexecutable="java -Xms4G -Xmx12G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=16M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=[https://mcflags.emc.gs](https://mcflags.emc.gs) -Daikars.new.flags=true -jar ${executable} nogui"
updateonstart="off"
```

Si necesitas aceptar el EULA rápidamente por comando:

```bash
sed -i 's/eula=false/eula=true/g' /root/minecraft-server/serverfiles/eula.txt
```
<div align="center"> Optimizado para despliegues rápidos en Codespaces. </div>


# 📦 Minecraft Bedrock

## 🛠️ Guía de Instalación Paso a Paso

### 1. Acceso Root
```bash
sudo su -
```

### 2. Dependencias del Sistema (Específicas para Bedrock)

Bedrock requiere ```libcurl``` y ```openssl``` para validar cuentas de Microsoft/Xbox Live:

```bash
apt update && apt install -y curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat-openbsd lib32gcc-s1 lib32stdc++6 libcurl4-openssl-dev
```


