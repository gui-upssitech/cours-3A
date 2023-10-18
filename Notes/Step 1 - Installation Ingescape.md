Tags: #ingescape

# Création du Dockerfile

On choisis d'installer Ingescape dans un container dedié pour avoir un environnement cloisonné. Pour ce faire on part d'une image de base ubuntu 20.04 dans laquelle on installe ingescape-circle

```dockerfile
FROM ubuntu:20.04

# Install prerequisites
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y build-essential qt5-default

# Install ingescape
ARG INSTALLER_PATH=/tmp/ingescape-installer.run
COPY ./packages/Ingescape-Circle-3.6.0-1-installer-linux64.run ${INSTALLER_PATH}

RUN chmod +x ${INSTALLER_PATH}
RUN ${INSTALLER_PATH} install --default-answer --accept-licenses --confirm-command
RUN rm ${INSTALLER_PATH}

# Copy license file
COPY ./packages/UPSSITECH_RSI.igslicense /root/UPSSITECH_RSI.igslicense
```

Premier problème : Le script ne se lance pas. 
Cause: Absence de `C++` et `Qt` sur l'image de base ubuntu.
Solution: Installation de `build-essential` et `qt5-default`

Deuxième problème : Erreur d'installation du script
```log
11.90 [11516] Operation \"Execute\" with arguments \"xdg-icon-resource; install; --context; mimetypes; --size; 48; /usr/share/icons/hicolor/48x48/apps/com.ingescape.circle.png; application-x-igsplatform\" failed: Execution failed (Unexpected exit code: 255): \"xdg-icon-resource install --context mimetypes --size 48 /usr/share/icons/hicolor/48x48/apps/com.ingescape.circle.png application-x-igsplatform\"

11.90 [11516] installationErrorWithCancel : Installer Error : Error during installation process (com.ingescape.circle):
```
Cause: programme `xdg-icon-resource` manquant
Solution: Installation de `xdg-utils`

# Lancement du container

Lancement du container en mode interactif et en partageant l'écran pour permettre de lancer des applications graphiques :
https://www.baeldung.com/ops/docker-compose-interactive-shell

Fichier `docker-compose.yml` :

```yml
version: '3'
services:
	ingescape:
		build: .
		image: upssitech/ingescape-project
		  
		# share screen with host to launch GUI programs
		environment:
			- DISPLAY=${DISPLAY}
		volumes:
			- /tmp/.X11-unix:/tmp/.X11-unix
		network_mode: host
		
		# make interactive
		stdin_open: true
		tty: true
```
