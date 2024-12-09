# Guía para Instalar y Configurar ZSH

Este documento describe los pasos necesarios para instalar y configurar ZSH, incluyendo el uso de Powerlevel10k y varios plugins. Además, se incluyen instrucciones para clonar este repositorio y configurar los archivos provistos.

## Contenido del Repositorio

Este repositorio contiene los siguientes archivos:

- `README.md`: Este archivo con la guía completa.
- `.zshrc`: Archivo de configuración principal de ZSH.
- `.p10k.zsh`: Archivo de configuración para Powerlevel10k.

## Requisitos Previos

Antes de comenzar, asegúrate de tener permisos de superusuario y acceso a una conexión a internet.

## 1. Clonar el Repositorio

Clona este repositorio para obtener los archivos de configuración:

```bash
git clone https://github.com/juancuellardev/zsh.git
cd zsh
```

## 2. Instalar ZSH

Ejecuta el siguiente comando para instalar ZSH:

### En Ubuntu/Debian

```bash
sudo apt update
sudo apt install zsh
```

### En Fedora

```bash
sudo dnf install zsh
```

### En macOS

```bash
brew install zsh
```

## 3. Configurar ZSH como Shell por Defecto

### 3.1 Consultar la Shell Actual

Verifica la shell actual:

```bash
echo $SHELL
```

### 3.2 Cambiar la Shell Predeterminada

Cambia ZSH como shell predeterminada:

```bash
chsh -s $(which zsh)
```

Cierra y vuelve a abrir la terminal para aplicar los cambios.

## 4. Copiar Archivos de Configuración

Copia los archivos del repositorio a tu directorio de usuario:

```bash
cp .zshrc ~/
cp .p10k.zsh ~/
```

## 5. Instalar Powerlevel10k

Clona el repositorio de Powerlevel10k y agrégalo a tu configuración de ZSH:

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```

Para configurar Powerlevel10k, inicia una nueva sesión de terminal:

```bash
zsh
p10k configure
```

## 6. Instalar Plugins de ZSH

### 6.1 `zsh-syntax-highlighting`

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.zsh/zsh-syntax-highlighting
echo 'source ~/.zsh/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh' >>~/.zshrc
```

### 6.2 `zsh-autosuggestions`

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git ~/.zsh/zsh-autosuggestions
echo 'source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh' >>~/.zshrc
```

### 6.3 `sudo.plugin.zsh`

```bash
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/plugins/sudo/sudo.plugin.zsh -P ~/.zsh
echo 'source ~/.zsh/sudo.plugin.zsh' >>~/.zshrc
```

## 7. Instalar Herramientas Adicionales

### 7.1 `lsd` (Listas con colores y íconos)

#### Ubuntu/Debian

```bash
sudo apt install lsd
```

#### Fedora

```bash
sudo dnf install lsd
```

#### macOS

```bash
brew install lsd
```

### 7.2 `bat` (Visualizador de archivos mejorado)

#### Ubuntu/Debian

```bash
sudo apt install bat
```

#### Fedora

```bash
sudo dnf install bat
```

#### macOS

```bash
brew install bat
```

### 7.3 `fzf` (Búsqueda interactiva)

Clona el repositorio e instala:

```bash
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
```

## 8. Recargar la Configuración de ZSH

Aplica los cambios ejecutando:

```bash
source ~/.zshrc
```

## 9. Verificar la Instalación

Para asegurarte de que todo funciona correctamente, verifica que los plugins están cargados revisando si sus directorios están activos. Por ejemplo:

```bash
ls ~/.zsh
```
Deberías ver los directorios correspondientes a los plugins instalados, como `zsh-syntax-highlighting` y `zsh-autosuggestions`.

Si quieres probar la funcionalidad de un plugin, como `zsh-autosuggestions`, simplemente escribe un comando que hayas usado antes para verificar las sugerencias automáticas.

## Notas Finales

- Asegúrate de tener instalado `git` y `wget`.
- Esta guía incluye configuraciones para diferentes plataformas; usa las instrucciones específicas para tu sistema operativo.

## Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para más detalles.