# Utilisez l'image officielle Nginx en tant que base
FROM nginx:latest

# Copiez le fichier de configuration Nginx
COPY nginx.conf /etc/nginx/nginx.conf

# Copiez le fichier welcome.blade.php dans le dossier html de Nginx
COPY welcome.blade.php /var/www/html/

# Exposez le port 80
EXPOSE 80

# Définissez la variable d'environnement pour le numéro de serveur
ENV APP_SERVER_NUMBER 1

# Démarrez Nginx lors du démarrage du conteneur
CMD ["nginx", "-g", "daemon off;"]
