========
Settings
========

This Middleware adds some settings to configure how to work with Crawlera.

CRAWLERA_APIKEY
---------------

Default: ``None``

Unique Crawlera API Key provided for authentication.

CRAWLERA_USER
-------------

*deprecated*

Default: ``None``

Old authentication user for the Crawlera service. It works with :ref:`CRAWLERA_PASS`.

CRAWLERA_PASS
-------------

*deprecated*

Default: ``None``

Old authentication password for the Crawlera service: It works with :ref:`CRAWLERA_USER`.

CRAWLERA_URL
------------

Default: ``'http://proxy.crawlera.com:8010'``

Crawlera instance url, it varies depending on adquiring a private or dedicated instance. If Crawlera didn't provide
you with a private instance url, you don't need to specify it.

CRAWLERA_MAXBANS
----------------

Default: ``400``

Number of consecutive bans from Crawlera necessary to stop the spider.

CRAWLERA_DOWNLOAD_TIMEOUT
-------------------------

Default: ``190``

Timeout for processing Crawlera requests. It overrides Scrapy's ``DOWNLOAD_TIMEOUT``.

CRAWLERA_PRESERVE_DELAY
-----------------------

Default: ``False``

If ``False`` Sets Scrapy's ``DOWNLOAD_DELAY`` to ``0``, making the spider to crawl faster. If set to ``True``, it will
respect the provided ``DOWNLOAD_DELAY`` from Scrapy.

CRAWLERA_DEFAULT_HEADERS
-----------------------

Default: ``{}``

Default headers added only to crawlera requests. Headers defined on ``DEFAULT_REQUEST_HEADERS`` will take precedence as long as the ``CrawleraMiddleware`` is placed after the ``DefaultHeadersMiddleware``*. Headers set on the requests have precedence over the two settings.

*This is the default behavior, ``DefaultHeadersMiddleware`` default priority is ``400`` and we recommend ``CrawleraMiddleware`` priority to be ``610``
