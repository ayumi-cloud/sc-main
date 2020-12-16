# Codename: Summer CMS (our OCMS update proposal)

## Table of Contents

|-- x
  |-- x

## Introduction

xxx



## Summer CMS Modules 👀

**Note: (*) This is a very brief overview of the modules and doesn't list the full features included in each module (this is intended to give users an overview picture).**

- **[Security Module](https://github.com/ayumi-cloud/sc-security-module)** - Enhanced security features including firewall, virus scanner, code checker, 2fa, u2f, security api's etc.

- **[Legal Module](https://github.com/ayumi-cloud/sc-legal-module)** - Legal features including tools for GDPR, ePrivacy, CCPA, Cookie Policy, Privacy Policy, Terms and Conditions, 2257 etc.

- **Protocol Module** - Intergrated features including HTTP/2, HTTP/3 with QUIC, IPFS, preloading, predictive prefetching etc.


- **Progressive Web Apps Module** - PWA and DPWA, Service workers, caching, manifest, banners, icons, badges, native api's etc.

- **AMP-HTML Module** - AMP-HTML features making it easier to create AMP-Content, AMP-Email and AMP-Stories etc.

- **Semantic Module** - Schema.org, JSON-LD, microformats, ontologies etc.

- **Frameworks Module** - Vanilla js ajax framework (no more jquery), intergrated features for Angular, React, Vue.js, Bootstrap, Web Components etc.

- **Developer Module** - .................. to do

- **CDN Module** - 

- **User Interface (UX) Module** - .................. to do

- **Performance Module** - 

- **Internalization Module** - 

- **Crypto and Web 3.0 Module** - 

- **Form Module** - 


...more modules will be uploaded




## Requirements 🚩

![PHP](https://github.com/ayumi-cloud/sc-security-module/blob/master/src/assets/images/php8.png)

This library has been optimized to work with php 7.4.x and 8.x. versions - we recommend upgrading from any lower php version.

### PHP 7.4.x Install Instructions

- PHP 7.4.x setup instructsions for Windows 10 found here: https://github.com/ayumi-cloud/sc-security-module/blob/master/docs/installation/setup.md#install-php-7-on-windows-10

### PHP 8.x Install Instructions

- [PHP 8.0 UPGRADE NOTES](https://github.com/php/php-src/blob/master/UPGRADING)

- [Migrating from PHP 7.4.x to PHP 8.0.x](https://www.php.net/manual/en/migration80.php)

- PHP 8.x setup instructsions found for Windows 10 here: https://github.com/ayumi-cloud/sc-security-module/blob/master/docs/installation/setup.md#install-php-8-on-windows-10

![laravel-logo](https://github.com/ayumi-cloud/sc-security-module/blob/master/src/assets/images/laravel.png)

### Laravel LTS

- Laravel 6.0 LTS (we currently use the latest LTS versions, due to the community consensus).

<p align="center"><img src="https://github.com/ayumi-cloud/sc-security-module/blob/master/src/assets/images/laravel-history.png"></p>

- Laravel 6.0 LTS to use [Laravel Passport](https://laravel.com/docs/6.x/passport).

- Laravel 7 to use [Laravel Airlock](https://laravel.com/docs/master/airlock). To learn more you can watch this video: [Laravel Airlock with Vue for SPA Auth](https://www.youtube.com/watch?v=D9oIu6jiYLk).

- Laravel 8 is Now Released, for full details of new features see here: https://laravel-news.com/laravel8 and https://laravel.com/docs/8.x/releases

## Servers 🔧

### Apache Server 🛠️

#### Enable the following Apache httpd modules

We have a dedicated Apache section for users using `.htaccess` some configurations won't have any effect if the appropriate modules aren't enabled. So, in order for everything to work as intended, you need to ensure the you have the following Apache modules enabled:

- [`mod_autoindex.c` (autoindex_module)](https://httpd.apache.org/docs/current/mod/mod_autoindex.html)
- [`mod_deflate.c` (deflate_module)](https://httpd.apache.org/docs/current/mod/mod_deflate.html)
- [`mod_expires.c` (expires_module)](https://httpd.apache.org/docs/current/mod/mod_expires.html)
- [`mod_filter.c` (filter_module)](https://httpd.apache.org/docs/current/mod/mod_filter.html)
- [`mod_headers.c` (headers_module)](https://httpd.apache.org/docs/current/mod/mod_headers.html)
- [`mod_include.c` (include_module)](https://httpd.apache.org/docs/current/mod/mod_include.html)
- [`mod_mime.c` (mime_module)](https://httpd.apache.org/docs/current/mod/mod_mime.html)
- [`mod_rewrite.c` (rewrite_module)](https://httpd.apache.org/docs/current/mod/mod_rewrite.html)
- [`mod_setenvif.c` (setenvif_module)](https://httpd.apache.org/docs/current/mod/mod_setenvif.html)

For more detailed information on configuration files and how to use them, please check the appropriate Apache documentation:

- https://httpd.apache.org/docs/current/configuring.html
- https://httpd.apache.org/docs/current/howto/htaccess.html

##### Support

 * Apache **2.4.10 or greater** (we are looking at adding some version 2.5 features in the near future)

#### Limits

> We have placed a `soft` **limit of 50Mb uncompressed or less** for the creation of the `.htaccess` file by this module. Developers and webmasters are allowed to go over the limit. This limit is set by the security module when generating the `.htaccess` file under its performance specs.

#### Default File Creation

The security module builds and creates the `.htaccess` file with the following sections:

- Backward Compatibility
- Cross Origins
- Errors
- Firewall
- HTTP Headers
- Media Types
- Rewrite Rules
- Security
- SSL
- Web Performance

(*) Disclaimer: Above is a brief list and not intended to be a complete list.

### Nginx Server 🛠️

Using the Nginx server settings has a few required steps to be able to work.

- [Nginx Beginners Guide](https://nginx.org/en/docs/beginners_guide.html)
- [Nginx Request Processing](https://nginx.org/en/docs/http/request_processing.html)

#### Support

- Nginx v**1.8.0**+

### Microsoft IIS Server 🛠️

The server settings target IIS7+ where replacement config is available for IIS8 (or simplification) it will be marked.

### Support

- **IIS7+**

## Databases
 
### MySQL

==== TO DO ===
 
 
 
 


### SQLite

- SQLite 3.7.11 or greater (we recommend the latest version of SQLite, which can be found here: [Latest Release](https://www.sqlite.org/index.html)).
  

=== TO DO ===
