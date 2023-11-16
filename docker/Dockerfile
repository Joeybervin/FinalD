
FROM php:8.2

# Installez les dépendances nécessaires
RUN apt-get update && \
    apt-get install -y \
        git \
        unzip \
        libzip-dev \
        libonig-dev \
        npm

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Installez Node.js et npm
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - && \
    apt-get install -y nodejs

# Définissez le répertoire de travail
WORKDIR /var/www/html

# Copiez les fichiers de l'application
COPY . /var/www/html

# Installez les dépendances PHP
RUN composer install

# Installez les dépendances npm et construisez les ressources frontend
RUN npm install && npm run dev

# Exécutez les commandes Laravel
CMD ["php", "artisan", "key:generate"]

# Exposez le port 9000 pour PHP-FPM
EXPOSE 9000
