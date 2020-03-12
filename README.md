# Utilisation du pattern

## Liste des étapes 

* Récupération du repo & vmise à en place du projet
  * Cloner le repo du pattern   `git clone git@github.com:O-clock-Universe/WP-Pattern-Composer.git`
    * Première solution  (nouveau projet commencé de 0)
      * Renommer le dossier avec le nom du projet souhaité  `mv WP-pattern-composer <nouveaunom>`
      * Se rendre dans le dossier nouvellement crée  `cd <nouveaunom>`
      * Supprimer le dossier  `.git` afin de ne pas écraser le repo pattern d'origine et de ne pas garder l'histoirique du pattern dans notre projet.   `sudo rm -R .git`
      * Initialiser git das le dossier du projet  `git init` 

    * Deuxième solution (projet partant d'un classroom)
      * Prendre tout se qui se trouve dans le dossier pattern et le copier/coller dans le dossier du nouveau projet.  (sauf le  ` .git`  et le ` README.md` )

* Installation de nos dépendances avec composer `composer install`
* Création de la BDD
* Création du fichier  ` wp-config.php`  à partir du fichier  ` wp-config-sample.php`
  * Renseigner les informations de connexion à la BDD
  * Renseigner les clés de salage [URL pratique] ( https://api.wordpress.org/secret-key/1.1/salt/ )
  * Renseigner la constante ` WP_CONTENT_URL` avec notre url locale
* Changer ler les droits des fichiers/dossiers de mon projet 
```bash
sudo chown -R <user>:www-data .
sudo find . -type f -exec chmod 664 {} +
sudo find . -type d -exec chmod 775 {} +
sudo chmod 644 .htaccess
```
* Se rendre sur l'url locoale de noter proje pour terminer l'installation de WordPress
*  :bulb: Penser à  changer del'urls :
   1. De la homede notre projet _( Admin  BO / Réglages / Adresse web du site (URL))_
   2. Des permaliens _( Admin BO / Réglages / Permaliens / Titre de publication )_

* La barre d'admin n'apparait plus sur le site
  * Nous avons changé les URL de WordPress, notre cookie n'est plus bon...
  Nous ne sommes plus connecté sur la home !
  * Se déconnecter du BO, puis se reconnecter.
  * Pour aller sur le BO:  ` http://.../wp/wp-admin/`