# INSTALLATION
# INSTALLATION DE MYSQL
# source: mysql-8.0.36.tar.gz
# voici les étapes pour l’installation de mysql via un code source :


1- désarchiver et décompresser 
$tar_-jxvf_ mysql-8.0.36.tar.gz
en resultat on obtient un dossier nommé « mysql-8.0.36 »


2- parametrage et dépendance 
construire un fichier nommer build en utilisant : 
$mkdir_build_&&_cd_build
besoin de cmake 
$sudo_apt-get_install_cmake
$cmake_..
error:besoin de build essential
$sudo_apt-get_install_build-essential
$cmake_..
error : besoin librairie blkid,boost,e2fslibs,boost-all,audit
$sudo_apt-get_install_libblkid-dev_e2fslibs-dev_libboost-all-dev_libbaudit-dev
$ cmake_.. 
 error:besoin de boost
téléchargements de boost :
$tar_-jxvf_boost_1_77_0.tar.bz2
$cd_boost_1_77_0.tar.bz2
dans le fichier bootstrap, il a y script bootstrap.sh
$./bootstrap.sh
obtention d’un executable nommé b2 qu’on va executer et partager dans l’arborescence à  à l’aide des commandes  
$.sudo_./b2
$.sudo_./b2 install
ensuite, on reviens dans /home/utilisateur/mysql-8.0.36/build 
$cd_/home/utilisateur/mysql-8.0.36/build 
dans ce fichier on execute la commande 
$cmake_..
error : besoin de pkgConfig
$sudo_apt-get_install_pkg-config
enfin, 
$cmake_..
on obtient un fichier « Makefile », et on execute :
$make
pour éparpiller les fichiers dans l’arborescence et terminer l’installation on utilise la commande :
$make_install
erreur : permission non accordé
$sudo su root 
#make install
 
INSTALLATION DE APACHE
code source : httpd-2.4.59.tar.gz
voici les étapes de l’installation de apache via un code source
1-pour décompresser,on utilise la syntaxe suivante :
     $gunzip_httpd-2.4.59.tar.gz 
après cela, on obtient le fichier archiver httpd-2.4.59.tar qu’on va désarchiver. Pour faire cela, on utilise :
		$tar_-xvf_httpd-2.4.59.tar
 et on obtient un dossier nommer httpd-2.4.59
2- on entre dans le dossier httpd-2.4.59 en utilisant la commande cd. Parmi les fichiers présents dans le dossier, on retrouve un dossier appelé README. Ce fichier énonce que pour trouver les étapes de l’installation, veuillez lire le fichier INSTALL. Dans ce fichier,on retrouve les indications suivantes :
	./configure --prefix=PREFIX 
	make
	make install
	prefix/bin/apachectl start 
3.dans le fichier httpd-2.4.59 on execute la commande suivante :
		$~/httpd-2.4.59.tar.gz : ./configure
erreur : abscence de APR
		$sudo_apt-get_install_libapr1_libapr1-dev
		$./configure 
erreur : abscence de la bibliothèque APR-util
		$sudo_apt-get-install_libaprutil1_liaprutil1-dev
		$./configure
erreur : abscence de pcre
		$sudo_apt-get_install_libpcre3_libpcre3-dev
4-on obtient un fichier appeler « Makefiles » dans httpd-2.4.59 et on execute les commandes suivantes :
		$make (pour compiler Makefiles)
		$sudo su root
		#make install (éparpiller les fichiers dans l’arborescence)
prefix : /usr/local/apache2
	pour verifier, on utilise :
	$/usr/local/apache2/bin/apachectl start


INSTALLATION DE PHP
CODE SOURCE:php-8.3.6.tar.gz
1.Pour décompresser et désarchiver:
    	$ tar_-zxvf_httpd-2.4.59.tar.gz
2.dépendance et installation    
	$ cd_php-8.3.6
 en se documentant voici les étapes à suivre :
    	$ ./configure
	erreur:besoin de xml-2.0
    	$ sudo apt-get install libxml2-dev
    	$ ./configure
    	erreur :besoin de sqlite3
    	$ sudo apt-get install libsqlite3-dev
    	$ ./configure
Pour compiler,on execute
    	$ sudo make 
Pour envoyer les fichiers dans l’arborescence
     	$ sudo su root
     	# make install
Pour vérifier :
	$ php -v
      
