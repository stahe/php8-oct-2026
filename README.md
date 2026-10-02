# Introduction au langage PHP 8 par l'exemple

📖 **Lire le tutoriel : [https://stahe.github.io/php8-oct-2026/](https://stahe.github.io/php8-oct-2026/)**

Ce cours apprend le langage [PHP](https://www.php.net) 8.5 **par l'exemple** : plus de 300 fichiers PHP, commentés ligne par ligne, dont les résultats d'exécution sont reproduits. Il part des bases du langage et va jusqu'aux services web et à une application web MVC.

C'est la réécriture, pour PHP 8, du cours [Introduction au langage PHP 7 par l'exemple](https://stahe.github.io/php7-juillet-2019/) (2019) : même plan, mêmes exemples, même fil rouge, mais un code d'aujourd'hui. Entre PHP 7 et PHP 8.5, beaucoup de fonctionnalités sont devenues **dépréciées** : le code de ce cours n'en utilise **aucune**. Tous les scripts ont été exécutés avec PHP 8.5 configuré pour tout signaler (`error_reporting = E_ALL`) : aucun message `Deprecated` n'apparaît dans leurs résultats.

| Cours PHP 7 (2019) | Cours PHP 8 (2026) |
|---|---|
| PHP 7.3 | PHP 8.5 |
| NetBeans | VS Code + PHP Intelephense |
| Codeception | PHPUnit 12 |
| Postman | curl |
| SwiftMailer, hMailServer | Symfony Mailer, Mailpit |
| fonctions `imap_*` (retirées du cœur de PHP en 8.4) | clients POP3 / IMAP écrits avec des sockets |
| attributs dynamiques, getters / setters | attributs typés, `readonly`, promotion des paramètres du constructeur |
| `switch`, constantes de classe | `match`, énumérations (`enum`) |
| `PDO::MYSQL_ATTR_*` (dépréciées en 8.5) | `PDO::connect()`, `Pdo\Mysql`, `Pdo\Pgsql` |
| `deny from all` (Apache 2.2) | un dossier `public/` et `Require all denied` (Apache 2.4) |

## Le plan du cours

| Chapitre | Contenu |
|---|---|
| Installation | Laragon 8 (PHP 8.5, Apache, MySQL, PostgreSQL, Redis), VS Code, Composer |
| Les bases de PHP | variables, typage strict, tableaux, chaînes, fonctions (arguments nommés, `match`, fonctions fléchées, opérateur pipe `\|>` de PHP 8.5), fichiers texte, JSON |
| Les classes, les interfaces | attributs typés, promotion du constructeur, `readonly`, crochets de propriétés et visibilité asymétrique (PHP 8.4), énumérations, `#[\Override]`, `clone` avec modifications (PHP 8.5), types intersection |
| Les exceptions et erreurs | la hiérarchie `Throwable` de PHP 8, les avertissements de PHP 7 devenus exceptions |
| Les traits, les applications en couches | réutiliser du code ; architecture [dao] / [métier] / [console] |
| Tests | PHPUnit 12 : fournisseurs de données par attributs, exceptions attendues |
| Bases de données | PDO avec MySQL 8 et PostgreSQL : ordres préparés, transactions |
| Fonctions réseau | TCP, HTTP, SMTP, POP3, IMAP, écrits avec des sockets puis avec des bibliothèques |
| Services web | pages dynamiques, JSON, paramètres GET / POST, sessions, authentification, HTTPS |
| XML | SimpleXML et la nouvelle API `Dom\XMLDocument` de PHP 8.4 |

## Le fil rouge : un calcul d'impôt en 13 versions

Tout le cours construit, version après version, un service de **calcul de l'impôt sur le revenu** :

- **versions 1 et 2** : un script, des fonctions, des fichiers texte et JSON ;
- **version 3** : des classes ; **version 4** : une architecture en couches, testée avec PHPUnit ;
- **versions 5 à 7** : les données fiscales dans une base MySQL, puis PostgreSQL, puis l'une ou l'autre ;
- **versions 8 à 11** : un service web et son client console : authentification, sessions, journal, courriel à l'administrateur en cas d'erreur, cache Redis, réponses JSON puis XML ;
- **version 12** : une application web **MVC** qui répond en JSON, en XML ou en HTML (Bootstrap 5), avec un client console du service JSON ;
- **version 13** : la sécurisation des fichiers de l'application (seul un dossier `public/` est visible du web).


## Technologies

PHP 8.5 · Apache 2.4 · MySQL 8.4 · PostgreSQL · Redis · Composer · PHPUnit 12 · Symfony HttpFoundation 8 · Symfony HttpClient 8 · Symfony Mailer 8 · Predis 3 · zbateson/mail-mime-parser 3 · Mailpit · Bootstrap 5 · Laragon 8 · VS Code

## Prérequis

- Avoir déjà programmé dans un langage quelconque.
- Windows et [Laragon](https://laragon.org) 8 (qui fournit PHP 8.5, Apache, MySQL, PostgreSQL, Redis et Composer), [VS Code](https://code.visualstudio.com) et son extension PHP Intelephense. Les instructions d'installation sont données au début du cours.

## Auteur

Ce cours et ses codes ont été rédigés par **Claude**, l'IA d'[Anthropic](https://www.anthropic.com) (octobre 2026), à la demande de Serge Tahé, à partir de son cours PHP 7 de 2019.
