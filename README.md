<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Installation de logiciels</title>
</head>
<body>
    <pre>
    <h1>INSTALLATION DE MYSQL</h1>
    Source: mysql-8.0.36.tar.gz
    Voici les étapes pour l'installation de MySQL via un code source :

    1. Désarchiver et décompresser :
    $ tar -jxvf mysql-8.0.36.tar.gz
    Résultat : un dossier nommé "mysql-8.0.36".

    2. Paramétrage et dépendance :
    $ mkdir build && cd build
    Besoin de CMake :
    $ sudo apt-get install cmake
    $ cmake ..
    error: besoin de build essential
    $ sudo apt-get install build-essential
    $ cmake ..
    error : besoin librairie blkid, boost, e2fslibs, boost-all, audit
    $ sudo apt-get install libblkid-dev e2fslibs-dev libboost-all-dev libaudit-dev
    $ cmake ..
    error : besoin de boost
    Téléchargements de boost :
    $ tar -jxvf boost_1_77_0.tar.bz2
    $ cd boost_1_77_0.tar.bz2
    Dans le fichier bootstrap, il y a un script bootstrap.sh
    $ ./bootstrap.sh
    Obtention d'un exécutable nommé b2 qu'on va exécuter et partager dans l'arborescence à l'aide des commandes :
    $ sudo ./b2
    $ sudo ./b2 install
    Ensuite, on revient dans /home/utilisateur/mysql-8.0.36/build
    $ cd /home/utilisateur/mysql-8.0.36/build
    Dans ce fichier, on exécute la commande :
    $ cmake ..
    error : besoin de pkgConfig
    $ sudo apt-get install pkg-config
    Enfin,
    $ cmake ..
    On obtient un fichier "Makefile", et on exécute :
    $ make
    Pour éparpiller les fichiers dans l'arborescence et terminer l'installation, on utilise la commande :
    $ make install
    Erreur : permission non accordée
    $ sudo su root
    # make install
<h1>INSTALLATION D'APACHE</h1>
    
    Code source : httpd-2.4.59.tar.gz
    Voici les étapes de l'installation d'Apache via un code source :

    1. Pour décompresser, on utilise la syntaxe suivante :
    $ gunzip httpd-2.4.59.tar.gz
    Après cela, on obtient le fichier archivé httpd-2.4.59.tar qu'on va désarchiver. Pour faire cela, on utilise :
    $ tar -xvf httpd-2.4.59.tar
    Et on obtient un dossier nommé httpd-2.4.59.

    2. On entre dans le dossier httpd-2.4.59 en utilisant la commande cd. Parmi les fichiers présents dans le dossier, on retrouve un dossier appelé README. Ce fichier énonce que pour trouver les étapes de l'installation, veuillez lire le fichier INSTALL. Dans ce fichier, on retrouve les indications suivantes :
    ./configure --prefix=PREFIX
    make
    make install
    prefix/bin/apachectl start

    3. Dans le fichier httpd-2.4.59, on exécute la commande suivante :
    $ ~/httpd-2.4.59.tar.gz : ./configure
    Erreur : absence de APR
    $ sudo apt-get install libapr1 libapr1-dev
    $ ./configure
    Erreur : absence de la bibliothèque APR-util
    $ sudo apt-get install libaprutil1 libaprutil1-dev
    $ ./configure
    Erreur : absence de PCRE
    $ sudo apt-get install libpcre3 libpcre3-dev

    4. On obtient un fichier appelé "Makefiles" dans httpd-2.4.59 et on exécute les commandes suivantes :
    $ make (pour compiler Makefiles)
    $ sudo su root
    # make install (éparpiller les fichiers dans l'arborescence)
    prefix : /usr/local/apache2
    Pour vérifier, on utilise :
    $ /usr/local/apache2/bin/apachectl start
<h1>INSTALLATION DE PHP</h1>
    
    
    Code source : php-8.3.6.tar.gz
    1. Pour décompresser et désarchiver :
    $ tar -zxvf httpd-2.4.59.tar.gz

    2. Dépendance et installation
    $ cd php-8.3.6
    En se documentant, voici les étapes à suivre :
    $ ./configure
    Erreur : besoin de xml-2.0
    $ sudo apt-get install libxml2-dev
    $ ./configure
    Erreur : besoin de sqlite3
    $ sudo apt-get install libsqlite3-dev
    $ ./configure
    Pour compiler, on exécute
    $ sudo make
    Pour envoyer les fichiers dans l'arborescence
    $ sudo su root
    # make install
    Pour vérifier :
    $ php -v
</pre>
</body>
</html>
