Watch List
==========

If you can think of it, then the chances of someone else already writing a library for it are fairly high.
The following is a list of vendors and/or open-source bundles/libraries/projects I've stumbled across that may provide
value in future client work. Mainly focused on Symfony (as this has the largest open-source community), but not limited
to.

- If a particular vendor is found to provide more than one potentially useful *project*, list the projects under a
  document section of that vendor.
- If a project is a bundle acting as an adapter for another library then just list the bundle project.
- Do not list any bundles that are included by default in the Symfony
  [standard edition](https://github.com/symfony/symfony-standard).

## [Doctrine Project](http://www.doctrine-project.org)

The number one vendor in the PHP community for libraries that deal with data; persistence, specification, cache, etc.
Doctrine is pretty well integrated into the Symfony standard edition already, however the following bundles are always
helpful for dealing with database development:

- [DoctrineMigrationsBundle](https://github.com/doctrine/DoctrineMigrationsBundle), for the safe and quick management of
  database migrations.
- [DoctrineFixturesBundle](https://github.com/doctrine/DoctrineFixturesBundle), for loading data fixtures
  programmatically. This data can be used for testing or could be the initial data required for the application to run
  smoothly, defined in code just like database structure is defined in migrations.

## [Friends of Symfony](http://friendsofsymfony.github.io)

The unofficial vendor for extending Symfony2 functionality.

- [FOSUserBundle](), the complete back-end for user functionality (login, registration, profiles, etc).
- [FOSMessageBundle](https://github.com/FriendsOfSymfony/FOSMessageBundle), messaging component featuring threaded
  conversations, spam detection, soft-deletion, message permissions, user inbox, etc. The only downside is that this
  bundle is currently looking for a new active maintainer.
- [FOSCommentBundle](https://github.com/FriendsOfSymfony/FOSCommentBundle), adds support for a threaded comment system.
  It gets a mention because it could be useful in a future project, but just like the messaging bundle it is currently
  looking for an active maintainer.
- [FOSRestBundle](https://github.com/FriendsOfSymfony/FOSRestBundle), one of the best libraries for creating RESTful
  APIs in Symfony2. This bundle will be wasted if you don't know the importance of REST when building APIs though,
  therefore I suggest reading [Building APIs You Won't Hate](https://leanpub.com/build-apis-you-wont-hate) by
  [Phil Sturgeon](https://philsturgeon.uk/) (there is a copy of it in the office).
- [FOSElasticaBundle](https://github.com/FriendsOfSymfony/FOSElasticaBundle), for integration of
  [Elasticsearch](http://www.elasticsearch.org/) in Symfony2. If client work will require fairly intensive search
  capabilities and will be deployed on a dedicated or virtualised server then Elasticsearch is the way to go.

## [JMS](http://jmsyst.com) (Johannes Schmitt)

- [JMSI18nRoutingBundle](http://jmsyst.com/bundles/JMSI18nRoutingBundle), allows you to create I18n
  (internationalisation) routes for your application. Meaning you can have different URLs (even domains) for different
  locales (languages/countries) that point to the same controller/action but changes the internal content `_locale`
  setting accordingly.
- [JMSTranslationBundle](http://jmsyst.com/bundles/JMSTranslationBundle), adds functionality that is geared towards
  content translators rather than developers, such as optimised message search algorithms, and a web-based interface to
  search, add and update messages in the application for any language that the application specifies it caters for.
- [JMSJobQueueBundle](http://jmsyst.com/bundles/JMSJobQueueBundle), allows you to schedule console commands as
  server-side jobs, including concurrent job execution, multiple queues, dependencies between jobs, and retry logic.

## [Sonata Project](http://sonata-project.org)

- [SonataNotificationBundle](http://sonata-project.org/bundles/notification), generate messages which can be retrieved
  by a generic backend and processed by specific actions - think an advanced version of *Chaser Actions*, more alike to
  Facebook Notifications.
- [SonataTranslationBundle](http://sonata-project.org/bundles/translation), if `JMSTranslationBundle` is the translation
  enhancer that caters for messages inside your application's code, then this bundle is the translation enhancer for
  content stored inside the application's database, or content repository.
- [SonataAdminBundle](http://sonata-project.org/bundles/admin), the infamous Sonata Admin; I've read mixed things about
  this bundle on the internet, people seem to either love it or hate it. This is the core bundle of several to provide
  an administrative section to a website; use
  [SonataDoctrineORMAdminBundle](http://sonata-project.org/bundles/doctrine-orm-admin/2-2/doc/index.html) to interact
  with a traditional relational database or
  [SonataDoctrinePhpcrAdminBundle](http://sonata-project.org/bundles/doctrine-phpcr-admin/master/doc/index.html) to
  interact with a content repository. I've included this because it may be a quick way to implement admin CRUD
  operations, but it does seem overly complex.

## [Sylius](http://sylius.org)

Sylius is an open-source project to build an e-commerce system in Symfony2; since it is decoupled, all functionality is
split up into individual, plug-and-play bundles to be dropped into any Symfony2 project. Documentation for the
[full list of bundles](http://docs.sylius.org/en/latest/bundles/index.html) is also available.

All bundles by Sylius are Symfony2 adapters for the extensive list of e-commerce libraries created by the same vendor,
Sylius. Although all of them are potentially useful for an e-commerce project, some noteworthy ones are:

- [SyliusCartBundle]() a generic cart solution that caters for any item that can be represented as a PHP object.
- [SyliusFlowBundle]() a form component that implements reusable-steps for building multi-page information aggregation
  such as checkouts, registrations, installations, etc.
- [SyliusInventoryBundle]() flexible inventory management including tracking.
- [SyliusShippingBundle]() a shipment component for the management of goods (both digital and physical), shipping
  methods, complex cost calculations, categorisation, and more - all based on product categorisation, weight,
  dimensions, location, target audience, etc.

## [Symfony CMF](http://cmf.symfony.com)

Although this project provides [decoupled bundles](http://symfony.com/doc/master/cmf/bundles/index.html) like Sylius,
this is less a list of useful bundles provided by a vendor and more the project in its entirety. To be honest, I don't
understand most of it as I've just scratched the surface - but enough to understand its potential.

- CMF stands for *Content Management Framework*, rather than CMS (a Content Management System such as
  [WordPress](https://wordpress.org), [Statamic](http://www.statamic.com), [Drupal](https://www.drupal.org) or
  [Joomla](http://www.joomla.org)).
- Imagine a CMS like WordPress that is programmicably configurable with a normal web interface like any other for
  creating and editing content. Built on top of PHPCR which is a *content repository* implemented inside a relational
  database such as MySQL, where most of its power comes from.
- Then imagine the content functionality is just one collection of bundles in a framework you can keep adding to. This
  is equivilent to one controller in [Yii](http://yiiframework.com), you just keep adding more and more controllers
  and actions until you have the rest of the functionality you want.
- CMF passes a bunch of variables to views just like any other controller, and we all know how easy it is to change a
  view.
- PHP Content Repository is like how you store content in a database, but on steroids. It has awesome things like tree
  hierarchy and access, versioning, branching (which they call workspaces), search nodes, capability discovery, and more.

... That's best way I can describe it.

> Symfony CMF is affliliated, but not written, by the creators of Symfony. They project is actually by a
> [company in Switzerland](http://www.liip.ch/en).

# Other Libraries

- [php-github-api](https://github.com/KnpLabs/php-github-api) by [KnpLabs](https://github.com/knplabs), a tested and
  documented, simple, object-orientated GitHub API client for PHP 5.3+
- [Retry](https://github.com/igorw/retry) by [Igor](https://github.com/igorw), a tiny library for retrying failing
  operations.
- [Stringy](https://github.com/danielstjules/Stringy) by [Daniel St. Jules](https://github.com/danielstjules), a PHP
  string manipulation library with multibyte support.
- [UUID](https://github.com/ramsey/uuid) by [Ben Ramsey](https://github.com/ramsey), a library for generating RFC 4122
  (version 1, 3, 4, and 5) universally unique identifiers in PHP 5.3+
- [Guzzle](https://github.com/guzzle/guzzle) by [Jeremy Lindblom](https://github.com/jeremeamia) and
  [Michael Dowling](https://github.com/mtdowling), a PHP HTTP client and framework for building RESTful web service
  clients.
- [Faker](https://github.com/fzaninotto/Faker) by [Francois Zaninotto](https://github.com/fzaninotto), a PHP library
  that generates fake data for you.
- [PHPSecLib](https://github.com/phpseclib/phpseclib) by [Jim Wigginton](https://github.com/terrafrost), the definitive
  PHP library for secure communications; including AES, RSA, SSH/SFTP, X.509, etc.
- [SncRedisBundle](https://github.com/snc/SncRedisBundle) by [Henrik Westphal](https://github.com/snc), integrate
  [Redis](http://redis.io) support into Symfony2 via [Predis](https://github.com/nrk/predis) or
  [PhpRedis](https://github.com/nicolasff/phpredis).
- [DNS](https://github.com/hoaproject/Dns) by [HOA Project](http://hoa-project.net/En), library to create a domain name
  resolver in PHP.
- [Parsedown](https://github.com/erusev/parsedown) and [Parsedown Extra](https://github.com/erusev/parsedown-extra) by
  [Emanuil Rusev](https://github.com/erusev), a better Markdown parser in PHP.
