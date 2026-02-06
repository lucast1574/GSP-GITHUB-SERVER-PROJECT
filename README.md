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
Este proyecto permite desplegar servidores de Minecraft (Java Edition) en **GitHub Codespaces** utilizando **LinuxGSM**. Está optimizado para ejecutarse directamente como usuario `root` para evitar problemas de permisos y maximizar la velocidad de despliegue.

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
