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


### 1. Dependencias del Sistema
```bash
sudo apt update && sudo apt install -y curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat-openbsd lib32gcc-s1 lib32stdc++6 steamcmd
```

### 2. Instalaicion de Java
```bash
sudo apt update
sudo apt install -y software-properties-common
```
```bash
sudo add-apt-repository -y ppa:openjdk-r/ppa
sudo apt update
```
- Java 8 version antiguas < 1.16.5

```bash
sudo apt install -y openjdk-8-jdk
```

- Java 17 para versiones 1.17 a 1.20.4

```bash
sudo apt install -y openjdk-17-jdk
```

- Java 17 para versiones 1.20.5 y superiores

```bash
sudo apt install -y openjdk-21-jdk
```


-Elige tu version de Java(Recomendado si instalas todas)

```bash
sudo update-alternatives --config java
```

### 3. Configurar Directorio

```bash
mkdir -p ./minecraft-server && cd ./minecraft-server
```

### 4. Descargar LinuxGSM

```bash
curl -Lo linuxgsm.sh https://raw.githubusercontent.com/GameServerManagers/LinuxGSM/master/linuxgsm.sh
```

```bash
chmod +x linuxgsm.sh
```

```bash
bash linuxgsm.sh mcserver
```

### 5. Instalacion Automatica 

```bash
./mcserver auto-install 
```

## Playit

Para obtener una IP fija sin depender del proxy HTTP de GitHub:

```bash
curl -SsL https://playit-cloud.github.io/ppa/key.gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/playit.gpg
```

```bash
echo "deb [signed-by=/etc/apt/trusted.gpg.d/playit.gpg] https://playit-cloud.github.io/ppa/data ./" | sudo tee /etc/apt/sources.list.d/playit-cloud.list
```

```bash
sudo apt update
sudo apt install playit -y
```

## 🎮 Comandos de Gestión

### Iniciar

```bash
./mcserver start 
```

### Consola

```bash
./mcserver console
```

### Detener

```bash
./mcserver stop 
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

### 1. Dependencias del Sistema (Específicas para Bedrock)

Bedrock requiere ```libcurl``` y ```openssl``` para validar cuentas de Microsoft/Xbox Live:

```bash
sudo apt update && sudo apt install -y curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat-openbsd lib32gcc-s1 lib32stdc++6 libcurl4-openssl-dev
```

### 2. Configurar Directorio y LinuxGSM (besserver)

```bash
mkdir -p ./bedrock-server && cd ./bedrock-server
```

```bash
curl -Lo linuxgsm.sh https://raw.githubusercontent.com/GameServerManagers/LinuxGSM/master/linuxgsm.sh
chmod +x linuxgsm.sh
bash linuxgsm.sh besserver
```

### 3. Instalacion Automatica

```bash
./besserver auto-install 
```

### 4. IP Playit.gg

IMPORTANTE: Minecraft Bedrock usa el protocolo UDP. El proxy nativo de GitHub Codespaces solo soporta HTTP/TCP. Es obligatorio usar Playit.gg para que los jugadores puedan entrar.

```bash
curl -SsL https://playit-cloud.github.io/ppa/key.gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/playit.gpg
```

```bash
echo "deb [signed-by=/etc/apt/trusted.gpg.d/playit.gpg] https://playit-cloud.github.io/ppa/data ./" | sudo tee /etc/apt/sources.list.d/playit-cloud.list
```

```bash
sudo apt update
sudo apt install playit -y
```

## 🎮 Comandos de Gestión Directa

### Iniciar

```bash
./besserver start
```

### Consola

```bash
./besserver console
```

### Detener

```bash
./besserver stop
```

### Detalles

```bash
./besserver details
```

# 💎 Hytale

## 🛠️ Guía de Instalación Paso a Paso

### 1. Acceso Root
```bash
wget [https://raw.githubusercontent.com/johnoclockdk/Hytale-Server-Installer/main/Hytale-Server](https://raw.githubusercontent.com/johnoclockdk/Hytale-Server-Installer/main/Hytale-Server) && chmod +x Hytale-Server && ./Hytale-Server install
```

##🎮 Diccionario de Comandos (CLI)

| Comando | Descripcion |
|---------|-------------|
| `./Hytale-Server install` | Install Hytale server |
| `./Hytale-Server start` | Start the server |
| `./Hytale-Server stop` | Stop the server |
| `./Hytale-Server restart` | Restart the server |
| `./Hytale-Server status` | Show server status & configuration |
| `./Hytale-Server console` | Open server console |
| `./Hytale-Server logs` | View live server logs |
| `./Hytale-Server update` | Update to latest version |
| `./Hytale-Server backup` | Create manual backup |
| `./Hytale-Server restore` | Restore from backup |
| `./Hytale-Server config` | Edit server configuration |
| `./Hytale-Server rotate-logs` | Manage and rotate server logs |
| `./Hytale-Server autobackup` | Toggle automatic backups |
| `./Hytale-Server autorestart` | Toggle automatic restarts |
| `./Hytale-Server self-update` | Update the installer script |
| `./Hytale-Server check-update` | Check for installer updates |
| `./Hytale-Server autoupdate` | Toggle automatic installer updates |
| `./Hytale-Server mods list` | List available and installed mods |
| `./Hytale-Server mods install <name\|number>` | Install a mod |
| `./Hytale-Server mods uninstall <name\|number>` | Uninstall a mod |
| `./Hytale-Server uninstall` | Remove completely |

💡 Run `./Hytale-Server` without arguments to show all commands.

## Playit

Usamos playit para crear un tunel al servidor 

```bash
curl -SsL https://playit-cloud.github.io/ppa/key.gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/playit.gpg
```

```bash
echo "deb [signed-by=/etc/apt/trusted.gpg.d/playit.gpg] https://playit-cloud.github.io/ppa/data ./" | sudo tee /etc/apt/sources.list.d/playit-cloud.list
```

```bash
sudo apt update
sudo apt install playit -y
```

# 🌲 Terraria


## 🛠️ Guía de Instalación Paso a Paso

Sigue estos bloques de comandos en la terminal:

### 1. Acceso Root y Dependencias

```bash
sudo apt update && sudo apt install -y curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat-openbsd lib32gcc-s1 lib32stdc++6 steamcmd
```

### 2. Configurar Directorio y LinuxGSM

```bash
mkdir -p ./terraria-server && cd ./terraria-server
```

```bash
curl -Lo linuxgsm.sh https://raw.githubusercontent.com/GameServerManagers/LinuxGSM/master/linuxgsm.sh
chmod +x linuxgsm.sh
bash linuxgsm.sh terrariaserver
```

### 3. Instalacion Automatica

```bash
./terrariaserver install
```

## 🎮 Comandos de Gestión (CLI)

Ejecuta estos comandos dentro de /root/terraria-server/:

| Comando | Descripcion |
|---------|-------------|
| `./terrariaserver start` | Inicia el servidor |
| `./terrariaserver stop` | Detiene el servidor|
| `./terrariaserver restart` | Reinicia el servidor |
| `./terrariaserver console` | Abre la consola en vivo (Salir: Ctrl+B luego D) |
| `./terrariaserver update` | Busca y aplica actualizaciones de SteamCMD|
| `./terrariaserver backup` | Crea un respaldo comprimido (tar bzip2) de todo el servidor |
| `./terrariaserver details` | Muestra puertos, contraseñas y archivos de configuración |

## ⚙️ Notas de Configuración

- Steam Login: Si el servidor te pide login, puedes editarlo en: /root/terraria-server/lgsm/config-lgsm/terrariaserver/common.cfg.

- Puertos: Terraria usa el puerto 7777. Recuerda usar Playit.gg para la conexión externa:

```bash
curl -SsL https://playit-cloud.github.io/ppa/key.gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/playit.gpg
```

```bash
echo "deb [signed-by=/etc/apt/trusted.gpg.d/playit.gpg] https://playit-cloud.github.io/ppa/data ./" | sudo tee /etc/apt/sources.list.d/playit-cloud.list
```

```bash
sudo apt update
sudo apt install playit -y
```
