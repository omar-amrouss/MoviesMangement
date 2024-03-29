<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[WebReinvent](https://webreinvent.com/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Jump24](https://jump24.co.uk)**
- **[Redberry](https://redberry.international/laravel/)**
- **[Active Logic](https://activelogic.com)**
- **[byte5](https://byte5.de)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

# Installation de l'application Gestion de films

Dans ce chapitre nous allons commencer à étudier les ressources qui permettent de créer des routes « CRUD » (Create, Read, Update, Delete) adaptées à la persistance de données. Comme exemple pratique nous allons prendre le cas d’une table de films.

Pour vous simplifier la vie voilà le code à la fin de cet article.

## Les Données

On repart d’un Laravel vierge et on crée une base comme on l’a vu précédemment.Appelons la par exemple laravel11 pour faire original. On renseigne le fichier .env en
conséquence :

- DB_CONNECTION=mysql
- DB_HOST=127.0.0.1
- DB_PORT=3306
- DB_DATABASE=laravel11_
- DB_USERNAME=root
- DB_PASSWORD=

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/d96063f0-cdec-4a3e-8399-1ac944fd84b6)

## Mise à jour et installation du composer
À l'aide du commande composer install, on fait l'installation du composter, et le publish du vendor file.

composer install

## La migration

On va créer avec Artisan les tables du la base de données, et les migrés :
![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/c20681a2-fb53-41e6-a724-926d50d6e2eb)


php artisan migrate

php artisan migrate:fresh

php artisan migrate:refresh

## Purpler la base de données
En utilisant la commande: php artisan db:seed

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/622d6956-a160-4746-8be9-084e064c7956)

## Lancer l'application
On va lancer l'application en utilisant la commande Artisan:

php artisan serve

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/8b549f07-887b-48ce-873c-1afe89cd4675)

## Navigation 
Lorsque on lance l'application : **http://127.0.0.1:8000**, on observe la page suivante de navigation:
![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/7ae8b3bd-612c-444e-9a51-f5340c507b63)


![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/4424c315-7b56-4608-aeca-3b3f6b60583e)

### Accès à l'application
Maitenant on va modifier l'URL de telle façon pour accéder à l'application: **http://127.0.0.1:8000/films**

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/5f249935-a35a-42e2-84cd-1c45eb26ff6d)

Voici la liste des films qu'on a dans la dase de données:

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/3a363136-f49c-46b3-b835-3a07a27b1c6e)

### Créer un film

Pour céer un film, il suffit de clicker sur le bouton : [Créer un film](http://127.0.0.1:8000/films/create)

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/6fea610a-c1dc-499d-bd09-1f250a8d8ed8)

### Modifier un film

Pour modifier un film, il suffit de clicker sur le bouton : [Modifier](http://127.0.0.1:8000/films/37/edit) du film choisi pour le modifier.

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/614bed1b-0d73-4607-8c6d-a96e8dbf5fb4)


### Lister ou voir un film

Pour voir les détaille du film, il suffit de clicker sur le bouton : [Voir](http://127.0.0.1:8000/films/37), du film désirer pour l'affichage.

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/ddd40d3b-6b44-4f6d-bd90-bd3ff0921b9c)

### Supprimer un film 

Pour supprimer un film, il faut clicker sur le bouton : [Supprimer] du film choisi pour le supprimer.

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/3581623a-168c-47fe-824d-a7b67a631eb6)

### Restaurer le film

Pour restaurer un film, il faut clicker sur le bouton : [Restaurer] du film choisi pour le restaurer.

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/5d04abb7-29d7-4296-9826-56ea303d07a5)

### Lister les catégories des films

![image](https://github.com/omar-amrouss/MoviesMangement/assets/133509604/105a1f5d-5560-4842-ba45-ff6b6c5dfe43)




















