# Image sur laquelle se bas ́ee - Elle sera t ́el ́echarg ́ee lors du build
FROM ubuntu:latest
# Auteur du Dockerfile - Optionnel
MAINTAINER Lucas Silva <lsilva@students.ephec.be>
# On installe bind et des utilitaires utiles au debuggage 

RUN apt update && apt upgrade -y && apt install bind9 bind9utils dnsutils net-tools -y\

# Copier un fichier named.conf qui se trouve dans le m^eme dossier que le Dockerfile
# vers le dossier /etc/bind/ de l'image.
COPY named.conf /etc/bind/
# Variable d'environnement qui sera disponible au sein du conteneur.

# Ouvrir/Exposer le port TCP & UDP du conteneur.
EXPOSE 53/tcp
EXPOSE 53/udp
# Commande realise au debut du container

CMD ["named", "-c", "/etc/bind/named.conf", "-g"]
