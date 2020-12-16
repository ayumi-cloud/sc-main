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









## Reporting a Vulnerability 💥

We strive to make the code accessible to a wide audience of beginner and experienced users.

We welcome bug reports, false positive alert reports, evasions, usability issues, and suggestions for new detections. Submit these types of non-vulnerability related issues via Github.

Please include your installed version and the relevant portions of your audit log.

False negative or common bypasses should [create an issue](https://github.com/ayumi-cloud/sc-main/issues/new) so they can be addressed.

Do this before submitting a vulnerability:

1) Verify that you have the latest version of Summer CMS.
2) Validate which Paranoia Level this bypass applies to. If it works in PL4, please send us an email.
3) If you detected anything that causes unexpected behavior of the engine via manipulation of existing provided rules, please send it by email.

We are happy to work with the community to provide CVE identifiers for any discovered security issues if requested.

If in doubt, feel free to reach out to us!

## Code of Conduct 💯

In order to ensure that the Summer CMS proposal community is welcoming to all, please review and abide by the [Code of Conduct](https://github.com/ayumi-cloud/sc-main/blob/master/CODE_OF_CONDUCT.md).

## For Future 🔮

Shoutout to people willing to contribute to this project. Please take a look at the [projects board](https://github.com/ayumi-cloud/sc-main/projects) for a list of things to be done.

## Browser Support ✅

The legal module has been tested in the following browsers:

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/chrome_48x48.png" alt="Chrome"><br>
      ✔
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/firefox_48x48.png" alt="Firefox"><br>
      ✔
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/safari_48x48.png" alt="Safari"><br>
      9+
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/edge_old_48x48.png" alt="Edge Legacy"><br>
      ✖ (1)
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/edge_48x48.png" alt="Edge"><br>
      ✔
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/internet-explorer_9-11_48x48.png" alt="Internet Explorer"><br>
      ✖ (2)
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/opera_48x48.png" alt="Opera"><br>
      ✔
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/samsung-internet_48x48.png" alt="Samsung"><br>
      ✔
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/uc_48x48.png" alt="UC"><br>
      ✔
    </td>
    <td align="center">
      <img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser/vivaldi_48x48.png" alt="Vivaldi"><br>
      3+
    </td>
  </tr>
</table>

### Notes

(1) Microsoft announced on 17 August that Edge Legacy will have its life support switched off on 9 March 2021, Summer CMS will support Edge Chromium only.

(2) Internet Explorer version 1-11, Summer CMS will not support due to only supporting `Evergreen` brwosers.

For a full list of browser support with Summer CMS, see here: [Browser Support](https://github.com/ayumi-cloud/sc-main/blob/main/docs/browser_support.md).

## Changelog 🏆

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributions, Feature Requests and Feedback ✨

We are actively inviting new contributors! To start, please read the [contribution guide](CONTRIBUTING.md).

This project is only possible thanks to the work of many dedicated volunteers. Everyone is encouraged to help in ways large and small. Here are a few ways you can help:

- Read the current content and help us fix any spelling mistakes or grammatical errors.
- Choose an existing [issue](https://github.com/ayumi-cloud/sc-legal-module/issues) on GitHub and submit a pull request to fix it.
- Open a new issue to report an opportunity for improvement.

If you find any bugs in the code or have any improvements in mind then feel free to generate a pull request.

**Note:** Please use Unit Testing and Coding Best Practices in order to have a valid pull request 😉

Patches and pull requests are encouraged. All code should follow the [PSR-1](https://www.php-fig.org/psr/psr-1/) and [PSR-2](https://www.php-fig.org/psr/psr-2/) style guidelines. **Please include unit tests whenever possible!**

### PSR ♻️

This legal module uses some PSR standards to be the most interoperable possible:

- [PSR-6](https://www.php-fig.org/psr/psr-6/) Caching Interface.
- [PSR-7](https://www.php-fig.org/psr/psr-7/) Standard interfaces to represent http requests, responses and uris.
- [PSR-17](https://www.php-fig.org/psr/psr-17/) Standard factories to create PSR-7 objects.
- [PSR-18](https://www.php-fig.org/psr/psr-18/) Standard interface to send a http request and return a response.

We also suggest using Cross-browser testing provided by BrowserStack (*) where a real-browser can't be used in-house.

<p align="center"><img src="https://github.com/ayumi-cloud/sc-main/blob/master/src/assets/images/browser-stack.png"></p>











## Copyright and License 📄

<p align="left"><img src="https://github.com/ayumi-cloud/sc-main/blob/main/src/assets/images/buttons/mit.svg"></p>

This is free software, licensed under the MIT, Open Source Initiative.

[⬆ back to top](#table-of-contents)

<p align="center"><img src="https://github.com/ayumi-cloud/sc-main/blob/main/src/assets/images/luv.png"></p>
